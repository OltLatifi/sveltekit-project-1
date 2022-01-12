<script context="module">
    export async function load({fetch}) {
        const response = await fetch("https://jsonplaceholder.typicode.com/posts")
        const guides = await response.json()
        if(response.ok) {
            return{
                props:{
                    // guides: guides,
                    guides
                }
            }
        }
        return{
            status: response.status,
            error: new Error("Could not fetch our API")
        }
    }
</script>

<script>
    export let guides;
</script>

<div class="guides">
    <ul>
        {#each guides as guide}
            <li><a href={`/guides/${guide.id}`}>{guide.title}</a></li>
        {/each}
    </ul>
</div>

<style>
    .guides {
        margin-top: 20px;
    
    }
    ul{
        list-style-type: none;
        padding: 0px;
    }
    a{
        display: inline-block;
        text-decoration: none;
        margin-top: 10px;
        padding: 10px;
        border: 1px dotted #ccc;
    }
</style>