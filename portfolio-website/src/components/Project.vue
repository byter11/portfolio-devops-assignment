<template>
    <div class="hello">
        <h1>Projects</h1>
    </div>
    <input type="text" v-model="filter" placeholder="Filter technologies"/>
    <article v-for="project in filteredProjects">
        <h2>{{ project.title }}</h2>
        <p> {{ project.description }} </p>
        <span v-for="tech in project.languages">#{{ tech + ' '}} </span>
    </article>
</template>

<script>
    import projects from '../data/projects.json';
    export default {
        name: 'Project',
        data() {
            return {
                projects,
                filter: ''
            }
        },
        computed: {
            filteredProjects() {
                console.log(this.filter);
                if (!this.filter)
                    return this.projects;

                return this.projects.filter(project => project.languages.map(l => l.toLowerCase()).includes(this.filter.toLowerCase()))
            }
        }
    }
</script>