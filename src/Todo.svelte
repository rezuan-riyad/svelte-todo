<script>
    export let todo;
    import { createEventDispatcher } from 'svelte';
    
    const dispatch = createEventDispatcher();

    const onDelete = (todoId) => {
        dispatch('delete-todo', todoId)
    }
</script>

<div class="display-card">
    <div class="des-section">
        <input type="checkbox" checked={todo.done} />
        <h5>{todo.title}</h5>
    </div>
    <button class="close-btn" on:click={() => onDelete(todo.id)}>X</button>
</div>

<style>
    .des-section{
		display: flex;
		align-items: center;
	}
	.des-section input{
		margin: 0;
		margin-right: 1rem;
	}
	.display-card{
		display: flex;
		align-items: center;
        justify-content: space-between;
	}
    .close-btn{
        border: none;
        outline: none;
        background-color: transparent;
        color: red;
        cursor: pointer;
        padding: 1rem;
    }
</style>