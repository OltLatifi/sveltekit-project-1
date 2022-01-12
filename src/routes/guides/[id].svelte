<script context="module">
    export async function load({fetch, params}) {
        const id = params.id;
        const response = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`)
        const guide = await response.json()
        if(response.ok) {
            return{
                props:{
                    // guides: guides,
                    guide
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
    export let guide;
</script>

<div class="guide">
    <h2>{guide.title}</h2>
    <p>{guide.body}</p>
</div>


<style>
    .guide{
        margin-top:40px;
        padding:10px;
        border: 1px dotted gray 
    }
</style>