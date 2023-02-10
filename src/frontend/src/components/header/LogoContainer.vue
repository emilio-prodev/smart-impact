<template>
    <div class="logo">{{ header_data }}</div>
</template>

<script>
export default {
    props: {
        header_data: String
    }
}
</script>


<style>
.logo {
    padding: 4px;
}
</style>