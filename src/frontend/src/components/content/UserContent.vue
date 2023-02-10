<template>
    <div v-if="user_data[0]">
        <h1>{{ user_data[0].item.owner.login }} gists </h1>

        <div class="gists-grid-main-container" v-for="(gists, key) in user_data" :key="key">
            <div class="gists-main-data">
                <img class="gists-user-avatar" :src="gists.item.owner.avatar_url" :alt="gists.item.owner.login" :title="gists.item.owner.login" />
                <span class="gists-data">
                    <span class="gists-user-username">{{ gists.item.owner.login }}</span> / <span>{{ gists.item.description }}</span>
                    <span class="language">PHP</span>
                </span>
                <div class="created">Created: {{ gists.item.created_at }}</div>
            </div>

            <div class="gists-forks-data">
                <span>Forked by: </span>
                <span>{{ gists.item.forks_url }}</span>
            </div>
        </div>
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
.gists-grid-main-container {
	display: grid;
	grid-template-areas:
		'gists-main-data'
		'gists-forks-data';
	padding: 15px;
    border-bottom: 1px solid #9e9e9e;
}
.gists-main-data {
    grid-area: gists-main-data; 
}
.gists-forks-data {
    grid-area: gists-forks-data;
    text-align: left;
    font-size: 9pt;
    margin-top: 10px;
    padding-left: 5px;
}

.gists-main-data {
	gap: 5px;
	padding: 5px;
    text-align: left;
}
.gists-data {
    color: #2196f3;
    font-weight: bold;
}

.gists-user-avatar {
    max-width: 30px;
    border-radius: 50%;
    border: 1px solid #9e9e9e;
    margin: -18px;
    margin-right: 5px;
    margin-left: 0;
}
.created {
    font-size: 8pt;
    margin-top: 1px;
    margin-left: 40px;
}
.language {
    float: right;
    font-size: 10pt;
    font-weight: normal;
    color: #ffffff;
    background-color: #4F5B93;
    padding: 5px 10px;
    border-radius: 5px;
}
h1 {
    font-size: 15pt;
    text-transform: uppercase;
}

</style>