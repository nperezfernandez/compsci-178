<script>
	//import #Reasusable component1 for tittle
	import Title from './Title.svelte';
	//import #Reasusable component2 for subtitle
	import Subtitle from './Subtitle.svelte';
	//import #Reasusable component3 for date
	import Date from './Date.svelte';

	//intiialize variables for todo list
  let todos = []; // (Think it can count as #async-Stateful #control flow but stronger examples also shown below)
  let newTodo = ""; // (Think it can count as #async-Stateful #control flow but stronger examples also shown below)

	//add to do funciton allow for a new to do to be added after the last one, used ChatGpt 3 tutorial
  function addTodo() {
    todos = [...todos, newTodo]; //#Reactive values and #control flow
    newTodo = "";
  }
	//function gotten from ChatGpt3 tutorial to delete to dos 
  function deleteTodo(index) {
    todos = todos.filter((_, i) => i !== index); //#Reactive values and #control flow
  }
  
</script>

<style>
.main {
	margin-left: auto;
	margin-right: auto;
	width: 600px;
}

button {
	background-color: gold;
	font-weight: bold;
	font-size: 16px;
	font-color: white;
}

.ButtonCustom {
        background-color: gold;
        font-weight: bold;
        font-size: 20px;
        font-color: white;
}


.inputs {
	width: 305px;
	margin-left: auto; 
	margin-right: auto;
}
</style>

<div class="main">
	<!--#Component-Property1-->
	<Title />
	<!--#Component-Property 2 -->
	<Subtitle /> 
	<!--#Component-Property 3 -->
	<Date />
	<div class="inputs">
		<input bind:value={newTodo}> <!--#Reactive #binding #controlful-->
		<button class="ButtonCustom" on:click={addTodo}> To-Do </button><!--#Binding #reactive -->

	<ul>
	{#each todos as todo, index} <!--controlFlow-loop got from the ChatGPT3 tutorial-->
		<li>
		{todo} <!--#Reactive-->
		<button on:click={() => deleteTodo(index)}>Delete</button> <!--#Binding #Event Handler-->
		</li>
	{/each}
	</ul> 
		</div>
</div>