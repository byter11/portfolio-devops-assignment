<template>
    <div class="hello">
     <h1>Education</h1>
    </div>
    <article v-for="entry in education">
        <h2>{{ entry.institution }}</h2>
        <p> {{ entry.degree }} </p>
        <span>{{ entry.grade }} </span>
    </article>
</template>

<script>
    import education from '../data/education.json';
    export default {
        name: 'Education',
        data() {
            return {
                education
            }
        }

    }
</script>