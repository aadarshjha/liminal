<style>
    /* h1 {
        color: red; 
    } */
</style>

<script>
    import marked from "../../node_modules/marked/marked.min.js"
    import { onMount } from "svelte";
    onMount(async () => {
		document.getElementById("content").innerHTML = marked("Marked in the browser\n\nRendered by **marked**. \n <code>test this is a test that i smore code etcthat eixsts siasdj;flads lkf sadklfj ;laskdf asfjkls;fjs;kfj ;lskj f;ljs df;ljs ;lkfj ;sdlkj f;laksj df;klasj fdkjas f;kjsa kjf s;dklfj ;klj</code>");
	}); 

</script>

<h1>Test</h1>

<div id="content">

</div>