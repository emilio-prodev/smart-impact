<template>
    <div v-if="user_data[0]">
        <h1>{{ user_data[0].item.owner.login }} gists </h1>

        <div></div>
    </div>

    <div v-else>
        No gists results for this user.
    </div>
</template>

<script>
export default {
    props: {
        user_data: Array
    }
}

</script>


<style>
h1 {
    font-size: 15pt;
    text-transform: uppercase;
}
</style>