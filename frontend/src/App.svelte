<script lang="ts">
  import io from "socket.io-client";

  const socket = io("http://localhost:3000");

  let counter1 = 0;
  let counter2 = 0;

  type CounterName = "counter1" | "counter2";

  const incrementCounter = (counterName: CounterName) => {
    socket.emit("increment", counterName);
  };

  socket.on("increment-counter1", () => {
    counter1 += 1;
  });

  socket.on("increment-counter2", () => {
    counter2 += 1;
  });
</script>

<div class="container">
  <div class="counter">{counter1}</div>
  <button class="increment" on:click={() => incrementCounter("counter1")}
    >Increment Counter 1</button
  >
</div>
<div class="container">
  <div class="counter">{counter2}</div>
  <button class="increment" on:click={() => incrementCounter("counter2")}
    >Increment Counter 2</button
  >
</div>

<style>
  .container {
    display: inline-block;
    padding: 20px;
    margin: 20px;
    border: 2px solid black;
    text-align: center;
  }

  .counter {
    font-size: 200px;
  }

  .increment {
    font-size: 20px;
  }
</style>
