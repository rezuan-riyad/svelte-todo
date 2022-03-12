<script>
  import { Link } from "svelte-routing";
</script>

<nav class="nav">
  <div class="navLink">
    <Link to="/"><span style="color: white;">Home</span></Link>
  </div>
  <div class="navLink">
    <Link to="todos">
      <span style="color: white;">Todos</span></Link>
  </div>
  <div class="navLink">
    <Link to="chat" class="navLink">
      <span style="color: white;">Chat</span></Link>
  </div>
</nav>

<style>
  nav {
    height: 10vh;
    box-sizing: border-box;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    background-color: #2b2a2a;
  }
  .navLink {
    padding: 0 1rem;
    color: white;
  }
</style>
