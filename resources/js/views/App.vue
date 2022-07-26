<template>
    <BaseHeader/>
    <!-- <ul>
        <li v-for="post in posts" :key="post.id">{{post.title}}</li>
    </ul> -->
</template>

<script>
import BaseHeader from '../components/macro/BaseHeader.vue';

export default {
    name: 'App',
    data(){
        return{
            posts:[]
        };
    },
    components:{
        BaseHeader,
    },
    created(){
        axios.get('http://127.0.0.1:8000/api/posts')
        .then((response) => {
            console.log(response.data);
            this.posts = response.data;
        })
        .catch((error) => {
            console.log(error);
        })
    }
}
</script>

<style>

</style>