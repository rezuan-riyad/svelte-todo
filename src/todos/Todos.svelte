<script>
  import Card from "../UI/Card.svelte";
  import Todo from "./Todo.svelte";
  import AddForm from "./AddForm.svelte";
  import { nanoid } from "nanoid";
  let todos = [
    {
      id: 1,
      title: "Go for shopping",
      done: false,
    },
    {
      id: 2,
      title: "Reading book.",
      done: true,
    },
  ];
  const handleDeleteTodo = (e) => {
    let todoId = e.detail;
    todos = todos.filter((td) => td.id != todoId);
  };
  const handleAddTodo = (e) => {
    let tempTodo = {
      id: nanoid(),
      title: e.detail,
      done: false,
    };
    todos = [tempTodo, ...todos];
  };
</script>

<div class="container">
	<h1 class="header">Todo List</h1>
	<AddForm on:submit-todo={handleAddTodo}/>
	{#each todos as todo}
		<Card>
			<Todo {todo} on:delete-todo={handleDeleteTodo} />
		</Card>
	{/each}
</div>


<style>
	.container{
		box-sizing: border-box;
		width: 500px;
		margin: 0 auto;
	}
	.header{
		text-align: center;
	}
</style>
