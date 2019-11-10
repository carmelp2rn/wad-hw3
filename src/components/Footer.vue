<template>
    <footer>
        <ul v-for="(link, index) in links" :key="index" class="links">
            <li>
                <a v-bind:href="link.link" target="_blank">{{link.name}}</a>
            </li>
        </ul>
    </footer>
</template>

<script>
    import Link from '../models/Link'
    export default {
        name: "Footer",
        data: () => {
            return{
                links: [new Link("https://ois2.ut.ee/", "ÕIS2"), new Link("https://courses.cs.ut.ee/", "Courses")]
            }
        }
    }
</script>

<style scoped>
    footer {
        padding-top:40px;
        height: 90px;
        position: fixed;
        bottom:0px;
        width: 100%;
		background-color: #001f3f;
    }
    footer .links {
        width: 100%;
        max-width: 200px;
        margin: 0 auto;
        color: #DDDDDD;
        font-size: 13px;
    }

    footer .links a {
        text-decoration: none;
        color: #acd7ff;
    }
</style>