<script lang="ts">
    type Todo = {
        id: string;
        title: string;
        content: string;
    };
    import TodoField from "../components/TodoField.svelte";
    import TodoList from "../components/TodoList.svelte";
    let todos: Todo[] = [{id:"00-000", title: "fist", content: "first todo in this list"}];

    function addTodo(title: string, content: string) {
        console.log('title: ' + title)
        console.log('content: ' + content)
        const newTodo: Todo = {
            id: Math.random().toString(36).substr(2, 9),
            title,
            content
        };
        todos = [...todos, newTodo];
        console.log("added todo", todos);
    }
</script>
<h1> This is todo app </h1>
<!-- Todo field component is adding an item by passing the callback function into child components. -->
<TodoField onSubmit={addTodo}></TodoField>

<!-- The Todo list is passing the array to the child and binding it to change the value of the parent's array. -->
<TodoList bind:todos={todos}></TodoList>
