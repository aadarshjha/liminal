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
        /* height: 12%; */
        height: 110px;
    }
    .large {
        font-size: 3em;
    }

    .nav {
        display: flex; 
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        height: 25px;
    }

 
</style>

<script>
    import marked from "../../node_modules/marked/marked.min.js"
    import potentialEmojis from "../json/emojis.json"; 
    import { onMount } from "svelte";
    import { Router, Link, Route } from "svelte-routing";
    import Note from "./Note.svelte"; 
    import About from "./About.svelte"; 
    import Imgs from "./Imgs.svelte"; 
    let url = ""; 
    // svelte routing SPA. 
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

<Router url="{url}">
    <nav class = "nav">
        <Link to="/"><h4>posts</h4></Link>
        <Link to="links"><h4>imgs</h4></Link>
        <Link to="about"><h4>about</h4></Link>
        
    </nav>
    <div>
      <Route path="about" component="{About}" />
      <Route path="about" component="{Imgs}" />
	  <Route path="/"><Note /></Route>
	</div>
  </Router>