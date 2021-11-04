<script>
	import { tasks } from './../store';

    let taskList = [];

    tasks.subscribe(tasks => {
        taskList = tasks;
    });

</script>

<section>
    <h2>Task List</h2>
    <div class="task-list">
        {#if taskList.length === 0 }
            <span class="muted">List is empty</span>
        {/if}

        {#each taskList as task, id }
            <div><strong># {id+1} - </strong> {task}</div>
        {/each}
    </div>
</section>

<style>
    .task-list div {
        border: 2px solid rgba(0,0,0,0.3);
        border-radius: 1rem;
        padding: 1rem;
        margin-top: 0.5rem;
    }

    .muted {
        color: rgb(0,0,0,0.3);
    }
</style>