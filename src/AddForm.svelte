<script>
    import { createEventDispatcher } from 'svelte';

    let text = "";
    const dispatch = createEventDispatcher();

    const onSubmit = (e) => {
        dispatch('submit-todo', text);
        text = "";
    }
</script>

<div class="add-form">
    <form on:submit|preventDefault|stopPropagation={onSubmit}>
        <input type="text" placeholder="Add New Todo" bind:value={text} />
        <button type="submit">Add Todo</button>
    </form>
</div>

<style>
    .add-form{
        width: 100%;
    }
</style>