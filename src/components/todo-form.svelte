<script>
	import { tasks } from './../store';

    let task = "";
    let taskList = [];
    let showError = false;

    tasks.subscribe(tasks => {
        taskList = tasks;
    });

    const addTask = () => {

        if ( task === "" ) {
            showError = true;
            return;
        }

        tasks.set([task, ...taskList]);
        task = "";
        showError = false;
    }
</script>

<section>
    <div>
        <h2>Add Task</h2>
    </div>
    <div>
        {#if showError}
            <div class="err">Please enter valid input.</div>
        {/if}
    
        <textarea class="textarea" bind:value={task}></textarea>
        <div class="button-panel">
            <button type="button" class="submit-btn" on:click={addTask}>+ Add To List</button>
        </div>
    </div>
</section>

<style>
	.textarea {
        max-width: calc(100% - 2rem);
        min-width: calc(100% - 2rem);
        min-height: 6rem;
        max-height: 6rem;
        outline: none;
        border: 2px solid rgb(0,0,0,0.2);
        border-radius: 1rem;
        padding: 1rem;
        resize: none;
    }

    .button-panel {
        text-align: right;
        padding-top: 1rem;
    }

    .submit-btn {
        background-color: aquamarine;
        padding: 1rem;
        outline: none;
        font-size: 1rem;
        font-weight: bold;
        border-radius: 1rem;
        border: 2px solid black;
        cursor: pointer;
    }

    .err {
        background-color: red;
        padding: 1rem;
        border-radius: 1rem;
        color: #fff;
        margin-bottom: 1rem;
    }

</style>