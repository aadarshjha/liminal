<style>
    .random-gen {
        display: flex; 
        flex-direction: row;
        /* background-color: red;  */
    }
    img {
        width: 40px;
        height: 40px;
        position: relative;
        top: 18px;
        left: 10px;
    }
</style>

<script>
    import marked from "../../node_modules/marked/marked.min.js"
    import { onMount } from "svelte";
    import axios from "../../node_modules/axios/dist/axios.js"; 

    onMount(async () => {
		document.getElementById("content").innerHTML = marked("Marked in the browser\n\nRendered by **marked**. \n <code>test this is a test that i smore code etcthat eixsts siasdj;flads lkf sadklfj ;laskdf asfjkls;fjs;kfj ;lskj f;ljs df;ljs ;lkfj ;sdlkj f;laksj df;klasj fdkjas f;kjsa kjf s;dklfj ;klj</code>");
    }); 

    let potentialEmojis = ["res/1.png", "res/2.png", "res/3.png", "res/4.png"];
    // let person = ;
</script>

<div class = "random-gen">
    <!-- extra lol -->
    <h1>Hello </h1>
    <img src={potentialEmojis[Math.floor(Math.random() * potentialEmojis.length)]} alt="emoji">
</div>

<h3>This is a portfolio.</h3>

<div id="content">

</div>