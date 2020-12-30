<style>
    .meta p {
        display: flex; 
        justify-content: flex-end;
        margin-top: 0px;
        color: rgb(160,160,160); 
    }

    #metadata {
        position: relative;
        top: -10px; 
    }
</style>

<script>
    import marked from "../../node_modules/marked/marked.min.js"
    import { onMount } from "svelte";
    import { nanoid } from '../../node_modules/nanoid/nanoid.js'; 
    import { Highlight } from 'svelte-highlight';
    import { javascript, typescript } from 'svelte-highlight/languages';
    import { github } from 'svelte-highlight/styles';
    import post from "../json/posts.json"; 
    import { storeFE, idIncrement } from './store.js';

    $: code = `const add = (a: number, b: number) => a + b;`;


    console.log(nanoid()); 
    onMount(async () => {
        for (let fetch of post) {

            let doc = document.getElementById("" + fetch["post_id"]); 

            for (let element of fetch['text']) {

                let key = Object.keys(element)[0]; 

                if(key == "header") {
                    doc.innerHTML += marked(element["header"]); 
                } else if (key == "body") {
                    doc.innerHTML += marked(element["body"]); 
                } else if (key == "code") {
                    // insert a Highlight component of code. 
                    let code = element["code"];
                    // console.log(code);  
                    doc.append(`<Highlight language="{typescript}" {${code}} />`); 
                } else if (key == "image") {
                    doc.innerHTML += marked(element["image"]); 
                }
            }
        }
	});
</script>

<!-- code highlighting. -->
<svelte:head>
  {@html github}
</svelte:head>


{#each post as card}
    <div class = "wrapper">
        <div id = {card["post_id"]}>
        </div>
        <div class = "meta">
            <p>{card["post_id"]}</p>
            <p id = "metadata">{card["meta"][0]}</p>
        </div>
    </div>
    
{/each}


<!--  -->


