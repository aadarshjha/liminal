<style>
    .card {
        /* background-color: lightgreen;  */
    }
    h1 {
        /* margin-top: px; */
        text-align: justify;

</style>

<script>
    import marked from "../../node_modules/marked/marked.min.js"
    import { onMount } from "svelte";

    onMount(async () => {
		// const res = await fetch(`https://jsonplaceholder.typicode.com/photos?_limit=20`);
        // photos = await res.json();
        // str = ""
        document.getElementById('card').innerHTML = marked('# Marked in the browser \n <img src = "res/moon.png" alt="a photo." />');
	});

    

</script>

<!-- fetches only from JSON -->

<div id = "card">
    <!-- <h1>A Test Note Of Human Life: Or, A Photo</h1>
    <img src = "res/moon.png" alt="a photo." />
    <p>The moon! A gentle thing of things, etc. its nice, amongst other things. the simple way in which it works</p> -->
</div>


