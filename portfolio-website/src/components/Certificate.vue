<template>
    <div class="hello">
        <h1>Certificates</h1>
    </div>
        <article v-for="certificate in certificates">
            <h2>{{ certificate.title }}</h2>
            <p> {{ certificate.issuer }} </p>
            <div>{{ certificate.credentialId }} </div>
            <a :href="certificate.url">Link</a>
        </article>
</template>

<script>
    import certificates from '../data/certificates.json';
    export default {
        name: 'Certificate',
        data() {
            return {
                certificates
            }
        }

    }
</script>