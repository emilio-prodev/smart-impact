<template>
    <div v-if="user_data[0]" class="user-info-grid-container">
        <img class="avatar" :src="user_data[0].item.owner.avatar_url" :alt="user_data[0].item.owner.login" :title="user_data[0].item.owner.login" />
        <span class="username">{{ user_data[0].item.owner.login }}</span>
        <span class="user-type">{{ user_data[0].item.owner.type }}</span>
    </div>

    <div v-else>
        No results...
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
.user-info-grid-container {
	display: grid;
	grid-template-areas:
		'avatar'
		'username'
		'user-type';
	gap: 5px;
	padding: 5px;
    justify-items: center;
}

.avatar {
    grid-area: avatar; 
    max-width: 150px;
    border: 1px solid #9e9e9e;
    border-radius: 50%;
}
.username {
    grid-area: username; 
    font-size: 17pt;
    color: #ffffff;
    background-color: #9e9e9e;
    padding: 6px;
    border-radius: 5px;
}
.user-type {
    grid-area: user-type; 
    font-style: italic;
    color: #616161;
}
</style>