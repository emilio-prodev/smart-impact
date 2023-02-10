<template>
    <div class="logo">{{ logo }}</div>
</template>

<script>
export default {
    props: {
        logo: String
    }
}
</script>


<style>
.logo {
    padding: 4px;
}
</style>