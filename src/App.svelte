<script>
	import { Router, Link, Route } from "svelte-routing";
	import Nav from "./UI/Nav.svelte"
	import Todos from "./todos/Todos.svelte";
	import Chat from "./chat/Chat.svelte";
	import Home from "./home/Home.svelte";
	import Messagebox from "./chat/Messagebox.svelte"

	export let url = "";
</script>

<Router url="{url}">
	<Nav />
	<div>
		<Route path="todos"><Todos /></Route>
		<Route path="chat"><Chat /></Route>
		<Route path="/"><Home /></Route>
		<Route path="chat/messagebox"><Messagebox /></Route>
	</div>
</Router>

<style>

</style>