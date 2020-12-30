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
    import "../../node_modules/highlight.js/styles/androidstudio.css";
    import marked from "../../node_modules/marked/marked.min.js"
    import { onMount } from "svelte";
    import { nanoid } from '../../node_modules/nanoid/nanoid.js'; 
    import hljs from "../../node_modules/highlight.js/lib/highlight.js"
    console.log(hljs)
    hljs.initHighlightingOnLoad(); 
    import post from "../json/posts.json"; 
    console.log(nanoid()); 
    // model.id = nanoid() //=> "V1StGXR8_Z5jdHi6B-myT"    

    onMount(async () => {
        // get all the id's 
        for (let fetch of post) {
            let doc = document.getElementById("" + fetch["post_id"]); 
            doc.innerHTML = marked(fetch['header']); 
            // then we assert the tag. 
            doc.innerHTML += marked(fetch['body']); 
        }
	});
</script>


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

<pre><code class="html">This is somesort of test</code></pre>


