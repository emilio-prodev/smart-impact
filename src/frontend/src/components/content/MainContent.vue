<template>
    <section>
        <side-bar :side_bar_data="main_content_data.side_bar_data"></side-bar>
        <user-content :user_data="main_content_data.user_data"></user-content>
    </section>
</template>

<script>
import SideBar from './SideBar';
import UserContent from './UserContent';

export default {
    components: {
        SideBar,
        UserContent
    },

    props: {
        main_content_data: Object
    }
}

</script>