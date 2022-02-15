<template>
    <ul>
        <learning-resource 
        v-for="res in resources" 
        :key="res.id" 
        :title="res.title" 
        :discription="res.discription"
        :link="res.link">
        </learning-resource>
    </ul>
</template>

<script>
import LearningResource from './LearningResource.vue'

export default {
    //Props to fetch/send resources data.
    //props: ['resources'],

    // privide resources KEY in TheResources,vue 38
    inject: ['resources'],
    //register LearningResources.
    components: {
        LearningResource
    }
}

</script>


<style scoped>

ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}

</style>