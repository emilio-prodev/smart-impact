<template>
    <header>
        <logo-container :header_data="header_data"></logo-container>
        <search-bar></search-bar>
    </header>
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