<template>
    <div>
        <h1>Posts</h1>
        <ul>
            <li v-for="post in posts" :key="post.id">
                UserID {{ post.userId }} <br>
                ID {{ post.id }} <br>
                Title {{ post.title }} <br>
                Body {{ post.body }}
                <hr>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'Posts',
        data() {
            return {
                posts: []
            }
        },
        async created() {
            const postsResponse = await fetch("https://jsonplaceholder.typicode.com/posts");
            const postsJson = await postsResponse.json();
            this.posts = postsJson
        }
    }
</script>