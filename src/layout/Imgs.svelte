<style>
    .images {
        padding-top: 20px;
    }
    .images img {
        margin-bottom: 10px; 
    }
    .gray  {
        color: rgb(160,160,160);
    }
</style>

<script>
    import imgs from "../json/imgs.json"; 
</script>


<div class = "images">
    {#each imgs as element}
        <div class = "test">  
            <img src={element['src']} alt="">
            <p><em>{element['desc']}</em> | <span class = "gray">{element['date']}</span></p>
        </div>
    {/each}

</div>