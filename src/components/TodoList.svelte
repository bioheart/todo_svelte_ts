<script lang="ts">
    type Todo = {
        id: string;
        title: string;
        content: string;
    };
    export let todos: Todo[];

    function removeTodo(id: string) {
        todos = todos.filter(todo => todo.id !== id);
    }

</script>
<div>
    <p>Total todos: {todos.length}</p>
</div>
{#each todos as { id, title, content }}
    <h2>{title}</h2>
    <p>{content}</p>
    <button on:click={()=>removeTodo(id)}>Remove</button>
    <hr>
{/each}