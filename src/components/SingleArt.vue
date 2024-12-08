<template>
    <div class="arts-flex">
        <div>
            <img :src="art.art_image" alt="Art Image"/>
        </div>
        <div class="art-details-flex">
            <h3>{{art.art_title}}</h3>
            <p id="artist-name">{{art.artist_name}}</p>
            <p>{{art.art_dimensions}}</p>
            <p class="art-info"><img src="https://img.icons8.com/?size=20&id=85102&format=png&color=000000" alt="Year Icon Image"/>{{art.year_of_creation}} &nbsp; &nbsp; &nbsp;{{art.art_medium}}</p>
            <p class="art-status" :style="{backgroundColor: this.getArtStatus(art.art_status)}">{{art.art_status}}</p>
        </div>
    </div>
</template>

<script>
    export default{
        name: "SingleArt",
        props:{
            art:Object
        },
        methods:{
             getArtStatus(artStatus){
                if(artStatus === "Available") return "#81b29a";
                else if(artStatus === "Display") return "#f4845f";
                else return "#bc4b51";
            }
        }
    }
</script>

<style scoped>
    .arts-flex{
        display:flex;
        align-items:center;
        border:transparent;
        border-radius:4px;
        padding:10px;
        box-shadow:0 4px 8px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
        margin: 10px auto;
        width:50%;
        gap: 5em;
    }
    .art-details-flex{
        display:flex;
        flex-direction:column;
        justify-content:center;
        align-items:center;
    }
    .arts-flex img{
        width: 300px;
        height: 250px;
    }
    .art-status{
        border:transparent;
        border-radius: 5px;
        padding:9px;
        color:white;
    }
    #artist-name{
        line-height: 1px;
        font-weight:bold;
    }
    .art-info img{
        width:20px;
        height:20px;
        vertical-align:middle;
    }
</style>