<style>
    .random-gen {
        display: flex; 
        flex-direction: row;
        /* background-color: red;  */
        /* background-color: red;  */
    }
    img {
        width: 40px;
        height: 40px;
        position: relative;
        top: 20px;
        left: 10px;
    }
    h3{
        /* background-color: red;  */
        position: relative;
        top: -30px; 
    }
    .header {
        display: flex; 
        flex-direction: row;
        justify-content: space-between;
        /* background-color: red;  */
    }
    .large {
        font-size: 3em;
    }
 
</style>

<script>
    import marked from "../../node_modules/marked/marked.min.js"
    import potentialEmojis from "../json/emojis.json"; 
    import { onMount } from "svelte";

    onMount(async () => {
		document.getElementById("content").innerHTML = marked("Marked in the browser\n\nRendered by **marked**. \n <code>test this is a test that i smore code etcthat eixsts siasdj;flads lkf sadklfj ;laskdf asfjkls;fjs;kfj ;lskj f;ljs df;ljs ;lkfj ;sdlkj f;laksj df;klasj fdkjas f;kjsa kjf s;dklfj ;klj</code>");
    }); 

    console.log(potentialEmojis); 

</script>

<div class = "header">
    <div class = "left">
        <div class = "random-gen">
            <!-- extra lol -->
            <h1>Hello </h1>
            <img src={potentialEmojis[Math.floor(Math.random() * potentialEmojis.length)]} alt="emoji">
        </div>
        
        <h3>This is a portfolio.</h3>
    </div>
    <div class = "right">
        <h1 class = "large">AJ</h1>
    </div>
</div>



<div id="content">

</div>