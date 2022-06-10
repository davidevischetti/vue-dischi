<template>
    <div>
        <img :src="img" :alt="albumName">
        <h3>{{albumName}}</h3>
        <span>{{text}}</span>
        <span>{{date}}</span>
    </div>
</template>

<script>

export default {
    name: "AlbumCard",
    props : ['img','text','date','albumName']
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    div {
        flex-basis: calc((100% - (20px * 10)) / 5);    
        margin: 20px;
        padding: 15px;
        display: flex;

        flex-direction: column;
        align-items: center;
        background-color: #2e3a46;

        img {
            width: 100%;
            object-fit: contain;
        }

        h3 {
            width: 100%;
            color: #fff;
            text-align: center;
            margin: 10px 0;
            font-size: 18px;
        }
        span {
            font-size: 12px;
            color: #666;      
        }
    }

</style>
