<script>
	import Header from "./layout/Header.svelte";
	import marked from "../node_modules/marked/marked.min.js"
	import "../public/style/main.css"; 
	import Note from "./layout/Note.svelte"; 
	import { onMount } from "svelte";
</script>

<style>
	#main {
		/* background-color: red;  */
		max-width: 520px;
		margin: auto;
		margin-top: 0px; 
		padding-top: 0px;
		height: 100%;
	}
</style>

<div id = "main">
	<Header />
	<Note />
</div>





