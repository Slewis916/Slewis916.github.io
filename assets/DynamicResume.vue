<template>
 <div id="DynamicResume">
    <h1>{{ metadata.basics.name }}</h1>
 </div> 
</template>

<script>
export default {
    name: 'DynamicResume',
    props: ['metaData'],
    created() {
        console.log("Exported Module");
    }
}

</script>