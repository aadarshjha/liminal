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
    // import "../../node_modules/highlight.js/styles/androidstudio.css";
    import marked from "../../node_modules/marked/marked.min.js"
    import { onMount } from "svelte";
    import { nanoid } from '../../node_modules/nanoid/nanoid.js'; 
    // import hljs from "../../node_modules/highlight.js/lib/highlight.js"
    // console.log(hljs)
    // hljs.initHighlightingOnLoad(); 

    import { Highlight } from 'svelte-highlight';
    import { javascript, typescript } from 'svelte-highlight/languages';
    import { github } from 'svelte-highlight/styles';

    $: code = `const add = (a: number, b: number) => a + b;`;

    import post from "../json/posts.json"; 
    console.log(nanoid()); 
    // model.id = nanoid() //=> "V1StGXR8_Z5jdHi6B-myT"    

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
            <!--  -->
        </div>
        <div class = "meta">
            <p>{card["post_id"]}</p>
            <p id = "metadata">{card["meta"][0]}</p>
        </div>
    </div>
{/each}


<!-- <Highlight language={typescript} `test` /> -->


