<script>
	import { error } from "@sveltejs/kit";

 let todoIteam = $state('');
 let todoList = $state([]);

    
    function additeam(event) {
        event.preventDefault();

        todoList = [...todoList, {
            text: todoIteam,
            done: false
            
        }];
        
        todoIteam= '';
    }
    $inspect(todoList);

    function removeItem (index){
        try{
        if(todoIteam.done==true){
            
        } else{

        }
        } catch {
            error;
        }
    }
</script>



<form onsubmit={additeam}>
    <input type ="text" name="todo-iteam" id="todo-iteam" bind:value={todoIteam}>
    <button type = 'submit'> Add To List </button>
</form>

<div class = "ww3">
    <ol>
        {#each todoList as item, index}
            <li class = "em">
                <span class:done={item.done}>{item.text}</span>
                <input type="checkbox" bind:checked={item.done} onclick={()=> removeItem}>
            </li>
        {/each}
    </ol>
</div>

<style> .em {
    padding: 0.5vw;
}

.done {
    color: gray;
    text-decoration: line-through;
}
</style>