<template>
  <ArtGalleryHeader />
  <ArtsList :artsList = artsList />
</template>

<script>
  import ArtGalleryHeader from "./components/ArtGalleryHeader.vue";
  import ArtsList from "./components/ArtsList.vue";

  export default{
    name: "App",
    components:{
      ArtGalleryHeader,
      ArtsList
    },
    data(){
      return{
        artsList:[]
      }
    },
    methods:{
      async fetchArtsList(){
        const response = await fetch("https://ganesh-node.onrender.com/api");
        const artsData = await response.json();
        return artsData[0].arts;
      },
    },
    async created(){
      this.artsList = await this.fetchArtsList();
    }
  }
</script>

<style scoped>
</style>