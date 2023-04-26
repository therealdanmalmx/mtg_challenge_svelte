
<script>
    export let color = 'red'
    export let value = 20;
    $: colorName = color.charAt(0).toUpperCase() + color.slice(1);

    const addQuantity = () => {
        if (value >= 20) {
            return;
        }
        value += 1;
    }

    const removeQuantity = () => {
        if (value <= 0) {
            return;
        }
        value -= 1;
    }

</script>

<div class="container pa">
    <div style="border: dashed 5px {color}" class="team">
        <h4 style="color: {color}">Team {colorName}: {value}</h4>
    <div>
        <button class="plus-button" on:click={addQuantity}>+</button>
        <button class="minus-button" on:click={removeQuantity}>-</button>
    </div>
    </div>
</div>

<style>
    * {
        padding: 0;
        margin: 0;
    }

    .team {
        width: 100%;
        min-height: 100px;
        padding: 1rem;
        font-weight: 700;
        text-align: center;
        border: dotted px red;
    }
    h2 {
        text-align: center;
    }
    h4 {
        font-weight: 500;
    }
    button {
        width: 30px;
        height: 30px;
        padding: .5rem;
        border: none;
    }
    .plus-button {
        line-height: 0;
        background-color: green;
    }
    .minus-button {
        line-height: 0;
        background-color: red;
    }
</style>