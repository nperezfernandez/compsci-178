<script>
    //used help from Sean Roades to figure out how to do #components and #properties
    export let Title;
    let name = 'CompSci 178'; 
  </script>

<style>
    .Title {
      text-align: center;
      
    }
  </style>
<!--#formatting string insirting name dynamically-->
<h1 class="title">To-DO List Homework for {name}! </h1> <!--#Property-->
  