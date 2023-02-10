<template>
    <div class="app main-grid-container">
        <main-header class="header" :header_data="header_data" @searchUser="search_user"></main-header>
        <main-content class="main-content" :user_data="user_data"></main-content>
		<main-footer class="footer" :footer_data="footer_data"></main-footer>
    </div>
	
</template>

<script>
import axios from 'axios';
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
		header_data: {
			logo: 'Smart Impact | Emil Test'
		},
		user_data: [],
		footer_data: 'Build by Emil for Smart Impact',
		search: 'vsouza'
	}),


	methods: {
		listar_gists() {
			axios.get('https://api.github.com/users/' + this.search + '/gists')
			.then((result) => {
				this.user_data = result.data.map((item) => {
					return {
						item: item
					}
				});
			})
			.catch(function (error) {
				if (error.response) {
					console.log(error.response.data);
					console.log(error.response.status);
					console.log(error.response.headers);
				}
			});
		},


		search_user(search) {
            this.search = search;
			this.listar_gists(1);
        }
    },


    mounted() {
        this.listar_gists(1);
    }
}
</script>


<style>
.main-grid-container > div {
	background-color: rgba(255, 255, 255, 0.8);
	text-align: center;
	padding: 15px;
}

.header { 
	grid-area: header; 
	box-shadow: 0 0 10px #ccc;
}
.main-content { 
	grid-area: main-content; 
	box-shadow: 0 0 10px #ccc;
}
.footer { 
	grid-area: footer;
	box-shadow: 0 0 10px #ccc;
	font-size: 8pt;
 }

.main-grid-container {
	display: grid;
	grid-template-areas:
		'header'
		'main-content'
		'footer';
	gap: 10px;
	padding: 10px;
}
</style>
