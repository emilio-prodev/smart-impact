<template>
    <div class="header-content-grid-container">
        <logo-container class="logo-container" :header_data="header_data"></logo-container>
        <search-bar class="search-box-container"></search-bar>
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
        header_data: String
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
