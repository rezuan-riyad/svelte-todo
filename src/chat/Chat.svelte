<script>
  import { onDestroy } from "svelte";
  import SelectUsername from "./SelectUsername.svelte";
  import socket from "../socket";
  import { navigate } from "svelte-routing"
  let all_users;

  const onUsernameSelection = (e) => {
    let username = e.detail;
    socket.auth = { username };
    socket.connect();
    navigate("/chat/messagebox", { replace: true })
  };

  // Connect-Error Event Handler
  socket.on("connect_error", (err) => {
    console.log(err);
  });

  // Remove Event Handler
  onDestroy(() => {
    socket.off("connect_error");
  });
</script>

<div>
  <SelectUsername on:username-selected={onUsernameSelection} />
</div>
