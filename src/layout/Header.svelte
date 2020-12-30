<style>

</style>

<script>
    import marked from "../../node_modules/marked/marked.min.js"
    import { onMount } from "svelte";
    onMount(async () => {
		document.getElementById("content").innerHTML = marked("Marked in the browser\n\nRendered by **marked**. \n <code>test this is a test that i smore code etcthat eixsts siasdj;flads lkf sadklfj ;laskdf asfjkls;fjs;kfj ;lskj f;ljs df;ljs ;lkfj ;sdlkj f;laksj df;klasj fdkjas f;kjsa kjf s;dklfj ;klj</code>");
	}); 

</script>

<h1>Hello.</h1> <img src="" alt="">
<h3>This is a portfolio.</h3>

<div id="content">

</div>