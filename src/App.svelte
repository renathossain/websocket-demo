<script>
    let counter1 = 0;
    let counter2 = 0;
</script>

<div class="container">
    <div class="counter">{counter1}</div>
    <button class="increment" on:click={() => (counter1 += 1)}
        >Increment Counter 1</button
    >
</div>
<div class="container">
    <div class="counter">{counter2}</div>
    <button class="increment" on:click={() => (counter2 += 1)}
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
