<template>
    <form role="search" method="get" class="form-inline">
        <div class="input-group p-2 bg-white border-bottom border-primary"  style="width:100%;">
            <label class="sr-only" for="search-field">Search this website for:</label> 
            <input id="search-field" type="search" placeholder="" value="" name="search" class="form-control border-0">
            <div class="input-group-btn">
                <button type="submit" class="btn bg-white border-0">
                    <span class="sr-only">Search</span>
                    <span class="fa fa-search text-primary" aria-hidden="true" aria-label="Search Buton"></span>
                </button>
            </div>
        </div>
    </form>
</template>
<script>
export default {

}
</script>