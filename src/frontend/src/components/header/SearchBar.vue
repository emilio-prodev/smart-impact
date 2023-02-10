<template>
    <div>
        <input type="text" v-model="search" placeholder="Search..." />
    </div>
</template>

<script>
export default {
    props: {
        search: String
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