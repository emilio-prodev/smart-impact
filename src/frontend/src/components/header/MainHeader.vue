<template>
    <div class="header-content-grid-container">
        <logo-container class="logo-container" :logo="header_data.logo"></logo-container>
        <search-bar class="search-box-container" :search_value="header_data.search"></search-bar>
    </div>
</template>

<script>
import LogoContainer from './LogoContainer';
import SearchBar from './SearchBar';

export default {
    components: {
        LogoContainer,
        SearchBar
    },

    props: {
        header_data: Object
    },


    data: () => ({
        show_profile_name_edit: false
    })
}

</script>


<style>
.logo-container { 
	grid-area: logo-container; 
    text-align: left;
}
.search-box-container { 
	grid-area: search-box-container; 
    text-align: right;
}
.header-content-grid-container {
	display: grid;
	grid-template-areas:
		'logo-container search-box-container search-box-container';
	gap: 10px;
}
</style>
