<script>
  let task = "";
  let tasks = [];
 

  // Listen for the enter press keyboard
  document.addEventListener("keypress", (k) => {
    if (k.keyCode == 13) {
      handleClick();
    }
  });

  // Handle click function
  const handleClick = () => {
    tasks.push(task)
    console.log(tasks);
    tasks = tasks;


    task = "";
  }

  

  const deleteElement = (task) => {
    tasks = tasks.filter((ele, index) => ele != task);

  

  }

  
 


</script>
<section class="main-section">
  


  <div class="container">
    <h2 class="header">Add Task</h2>
    <div class="input-row">
      <input type="text" class="addTask" id="addTask"  bind:value={task} >
      <button class="add" on:click={() => {
        handleClick();
      }}>Add Task</button>
      
    </div>
    
    <div class="task">
      {#each tasks as t, index}
        <div class="task-container">
          <h2 class="task-text">{t}</h2>

          <button class="delete" on:click={() => deleteElement(t)}>Delete</button>
        </div>
        {:else}
          <p class="no Task">No Task</p>
      {/each}
      
    </div>
  </div>

</section>