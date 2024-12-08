<template>
    <div v-for="art of artsList" :key="art.art_id">
        <SingleArt :art = art />
    </div>
</template>

<script>
    import SingleArt from "./SingleArt.vue";
    export default{
        name: "ArtsList",
        components:{
            SingleArt
        },
        props:{
            artsList:Array
        }
    }
</script>

<style>
</style>