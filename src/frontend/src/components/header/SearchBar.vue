<template>
    <div>
        <input type="text" v-model="search" placeholder="Search..." @keyup="search_user" />
    </div>
</template>

<script>
export default {
    data: () => ({
		search: ''
	}),


    emits: [
        'searchUser'
    ],


    methods: {
        search_user() {
            this.$emit('searchUser', this.search);
        }
    }
}
</script>


<style>
input {
    width: 100%;
    max-width: 600px;
    height: 15px;
    border: 1px solid #cbbebe;
    border-radius: 4px;
    padding: 5px;
}
</style>