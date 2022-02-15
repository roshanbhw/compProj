<template>
    <base-card>
        <base-button 
            @click="setSelectedTab('stored-resources')" 
            mode="flat">Stored Resources</base-button>
        <base-button 
            @click="setSelectedTab('add-resource')" 
            mode="flat">Add Resource</base-button>
    </base-card> 
    <component :is="selectedTab"></component>   
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue'

export default {
    components: {
        StoredResources,
        AddResource
    },
  data() {
      return {
          selectedTab: 'stored-resources',
          storedResources: [
                {
                    id: 'official-guide',
                    title: 'Official Guide',
                    discription: 'The offical Vue.js documentation',
                    link: 'https://vuejs.org'
                },
                {
                    id: 'google',
                    title: 'Google',
                    discription: 'Google to Learn',
                    link: 'https://google.com'
                },

            ],         
    };
  },
  provide() {
      return {
          resources: this.storedResources
      };
  },
  methods: {
      setSelectedTab(tab) {
          this.selectedTab = tab;
      }
  }
}
</script>

<style>

</style>