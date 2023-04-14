<template>
    <img alt="Vue logo" src="./assets/logo.png">
    <component :is="currentView" />
</template>

<script>
    import '@picocss/pico'
    import Home from './components/Home.vue'
    import Project from './components/Project.vue'
    import Education from './components/Education.vue'

    const routes = {
        '/': Home,
        '/projects': Project,
        '/education': Education
    }

    export default {
        name: 'App',
        components: {
            Home
        },
        data() {
            return {
                currentPath: window.location.hash
            }
        },
        computed: {
            currentView() {
                return routes[this.currentPath.slice(1) || '/'] || NotFound
            }
        },
        mounted() {
            window.addEventListener('hashchange', () => {
                this.currentPath = window.location.hash
            })
        }
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
