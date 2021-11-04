<script>
	import ToDoForm from './components/todo-form.svelte';
	import TaskList from './components/todo-list.svelte';
</script>

<main>
	
	<div class="container">
		<ToDoForm/>
		<TaskList/>
	</div>

</main>

<style>
	main {
		width: 100vw;
		height: 100vh;
	}

	.container {
		width:100%;
		max-width: 30rem;
		padding: 2rem;
		border-radius: 1rem;
		background-color: #ffffff;
		box-shadow: 1px 1px 5px rgba(0,0,0,0.3);
		position: absolute;
		left: 50%;
		top: 50%;
		transform: translate(-50%, -50%);
	}
</style>