<template>
    <div class="app">
        <main-header :header_data="header_data"></main-header>
        <main-content :main_content_data="main_content_data"></main-content>
		<main-footer :footer_data="footer_data"></main-footer>
    </div>
</template>

<script>
import MainHeader from './components/header/MainHeader';
import MainContent from './components/content/MainContent';
import MainFooter from './components/footer/MainFooter';

export default {
	components: {
        MainHeader,
		MainContent,
		MainFooter
    },

	data: () => ({
		header_data: 'Smart Impact | Emil Test',
		main_content_data: {
			side_bar_data: 'Side Bar',
			user_data: 'Content'
		},
		footer_data: 'Footer'
	})
}
</script>

<style>

</style>
