<template>
    <DynamicResume :metaData ="ResumeData"/>
</template>


<script>
import DynamicResume from './assets/DynamicResume.vue';
import JSONData from './assets/resume.json';


export default {
    name: 'App',
    components: {
        DynamicResume
    },
    data() {
        return {
            ResumeData:JSONData,

        };
    },


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