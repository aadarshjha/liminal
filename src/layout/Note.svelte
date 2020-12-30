<style>
    .card {
        /* background-color: lightgreen;  */
    }
    h1 {
        /* margin-top: px; */
        text-align: justify;
    }
</style>

<script>
    import marked from "../../node_modules/marked/marked.min.js"
    import { onMount } from "svelte";
    import { nanoid } from '../../node_modules/nanoid/nanoid.js'; 
    import post from "../json/posts.json"; 
    // console.log(nanoid()); 
    // model.id = nanoid() //=> "V1StGXR8_Z5jdHi6B-myT"    

    onMount(async () => {
		// const res = await fetch(`https://jsonplaceholder.typicode.com/photos?_limit=20`);
        // photos = await res.json();
        // str = ""
        // document.getElementById('card').innerHTML = marked('# Marked in the browser \n <img src = "res/moon.png" alt="a photo." /> <p>This is a test this is a setup etasd;fka skfj ;aks </p> \n #### part 3 why croes die <code>hello world a;lksdf ksd laks fjaslfksdklfsd fadsfj dslk;f sflksdlf sdkfja ;lskf ;aksfkl</code>');

        // get all the id's 
        for (let fetch of post) {
            document.getElementById("" + fetch["post_id"]).innerHTML = marked(fetch['body']); 
        }
	});

    

</script>

<!-- fetches only from JSON -->


{#each post as card}
    <div class = "wrapper">
        <div id = {card["post_id"]}>

        </div>
        <div class = "meta">
            <p>{card["post_id"]}</p>
        </div>
    </div>
{/each}

