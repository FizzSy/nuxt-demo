<template>
    <div class="container">
        <div>
            <Logo />
            <h1 class="title">
                nuxt-demo
            </h1>
            <div v-for="item in list" :key="item.ID">{{item.MALL_CATEGORY_NAME}}</div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    data() {

    },
    async asyncData({ req, params, $axios }) {
        let res = await axios.get('http://api.kaneki.com.cn/shopping/goods/getCateGoryList');
        return { list: res.data.message };
    },
}
</script>

<style>
.container {
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.title {
    font-family: 'Quicksand', 'Source Sans Pro', -apple-system,
        BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial,
        sans-serif;
    display: block;
    font-weight: 300;
    font-size: 100px;
    color: #35495e;
    letter-spacing: 1px;
}

.subtitle {
    font-weight: 300;
    font-size: 42px;
    color: #526488;
    word-spacing: 5px;
    padding-bottom: 15px;
}

.links {
    padding-top: 15px;
}
</style>
