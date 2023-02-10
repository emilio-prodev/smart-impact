<template>
    <div class="main-content-grid-container">
        <side-bar class="side-bar" :side_bar_data="main_content_data.side_bar_data"></side-bar>
        <user-content class="user-content" :user_data="main_content_data.user_data"></user-content>
    </div>
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


<style>
.side-bar { 
	grid-area: side-bar; 
    border-right: 1px solid hsl(0, 0%, 59%);
}
.user-content { 
	grid-area: user-content; 
}

.main-content-grid-container {
	display: grid;
	grid-template-areas:
		'side-bar user-content user-content user-content';
	gap: 10px;
}
</style>