<style>
    .card {
        /* background-color: lightgreen;  */
    }
    h1 {
        /* margin-top: px; */
        text-align: justify;
    }
    .wrapper {
        /* background-color: red;  */
        /* display: flex; */
        /* flex-direction: column; */

    }

    .meta p {
        /* background-color: blue; */
        display: flex; 
        justify-content: flex-end;

        margin-top: 0px;
        color: rgb(160,160,160); 
    }
    .meta {
        /* background-color: red;  */
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
            let doc = document.getElementById("" + fetch["post_id"]); 
            doc.innerHTML = marked(fetch['header']); 
            // then we assert the tag. 
            doc.innerHTML += marked(fetch['body']); 
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
            <p>{card["meta"][0]}</p>
        </div>
    </div>
{/each}

