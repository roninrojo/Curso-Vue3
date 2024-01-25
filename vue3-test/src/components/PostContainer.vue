<template>
    <ul>
        <li v-for="menuItem in menu" :key="menuItem.id">
           {{menuItem.name}}
        </li>
    </ul>
    <div v-if="numPost < minPost"> Hay menos de 3 post</div>
    <div v-else> Hay <span :class="{green : numPost > minPost}">{{numPost}}</span> post</div>
    <div class="post-container">
        <PostCard v-for="post in posts" :key="post.index" :title="post.title" :content="post.content"/>
    </div>
</template>
<script setup>
import PostCard from './PostCard.vue';
const menu = [
    {
        id: 2,
        name: "Home"
    },
    {
        id: 2,
        name: "Post"
    },
    {
        id: 3,
        name: "About"
    }
]
let posts = [
    {
        title: "titulo 1",
        content: "Contenido 1. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
    },
    {
        title: "titulo 2",
        content: "Contenido 2. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
    },
    {
        title: "titulo 3",
        content: "Contenido 3. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
    },
    {
        title: "titulo 4",
        content: "Contenido 4. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
    }
]
let numPost = posts.length;
const minPost = 3

</script>
<style scoped>
    ul {
        margin: 20px auto;
    }
    .post-container {
        display: flex;
        gap: 10px;
    }
    .green {
        color:aquamarine
    }
</style>