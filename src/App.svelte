<script>
	import Header from "./layout/Header.svelte";
	import marked from "../node_modules/marked/marked.min.js"
	import { onMount } from "svelte";
	// import "../node_modules/github-markdown-css/github-markdown.css"

	onMount(async () => {
		document.getElementById("content").innerHTML = marked("# Marked in the browser\n\nRendered by **marked**. \n <code>test this is a test that i smore code etcthat eixsts siasdj;flads lkf sadklfj ;laskdf asfjkls;fjs;kfj ;lskj f;ljs df;ljs ;lkfj ;sdlkj f;laksj df;klasj fdkjas f;kjsa kjf s;dklfj ;klj</code>");
	}); 

</script>


<style>
 

</style>

<main class="markdown-body">
	<Header />
	<div id = "content">

	</div>

</main>


