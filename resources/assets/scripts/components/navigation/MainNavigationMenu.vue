<template>
    <ul>
        <li v-for="navitem in mainNav" v-bind:key="navitem.ID" class="nav-item" :class="{'dropdown': navitem.children.length > 0 }">
            <span v-if="navitem.url == '' || navitem.url == '#'" :class="'nav-link ' + navitem.classes" >{{ navitem.title }}</span>
            <a v-else :href="navitem.url" :class="'nav-link ' + navitem.classes" :target="navitem.target" :rel="getRel(navitem)" >{{ navitem.title }}</a>
            <ul class="dropdown-menu" v-if="navitem.children.length > 0" >
                <li v-for="(child, i) in navitem.children" v-bind:key="i">
                    <a :href="child.url" :class="'dropdown-item ' + child.classes" :target="child.target" :rel="getRel(navitem)" >{{ child.title }}</a>
                    <div class="dropdown-submenu" v-if="child.children.length > 0" >
                        <div v-for="(c, i) in child.children" v-bind:key="i" class="submenu-link">
                            <a :href="c.url" :class="'dropdown-item ' + c.classes" :target="c.target" :rel="getRel(navitem)" >{{ c.title }}</a>
                        </div>
                    </div>
                </li>
            </ul>
        </li>
    </ul>
</template>

<script>
    export default {
        props: {
            mainNav: {}
        },
        methods: {
            getRel(item){
                return (item.target == '_blank' ? 'noreferrer' : null)
            }
        }
    }
</script>
<style lang="scss" >
    .main-navigation .dropdown:hover .dropdown-menu {
        display: flex;
    }
</style>