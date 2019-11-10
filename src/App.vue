<template>
    <main id="app">
        <Header></Header>
        <section id="container">
            <section id="main">
                <div class="content">
                    <Profile :gpa="gpa" ref="profile"/>
                    <Courses/>
                </div>
                <Controls @toggle="toggle"/>
            </section>
        </section>
        <Footer/>
    </main>
</template>

<script>
    import Controls from "./components/Controls";
    import Profile from "./components/Profile";
    import Header from "./components/Header";
    import Courses from "./components/Courses"
    export default {
        name: 'app',
        components: {
            Controls,
            Profile,
            Header,
            Courses,
        },
        methods: {
            toggle: function () {
                this.$refs.profile.toggleProfile();
                this.$refs.courses.toggleCourses();
            },
        },

    }
</script>

<style>
    * {
        box-sizing: border-box;
        font-family: 'Livvic', sans-serif;
    }

    html, body {
        padding: 0;
        margin: 0;
        width: 100%;
        height: 100%;
        background-color: #eaeaea;
    }

    main {
        position: relative;
        min-height: 100%;
        padding-bottom: 110px;
    }

    #container {
        width: 80%;
        max-width: 900px;
        min-width: 320px;
        padding: 15px;
        background-color: #ffffff;
        margin: 0 auto;
    }

    .content {
        padding: 10px;
        border: 1px solid #cbcbcb;
    }

</style>
