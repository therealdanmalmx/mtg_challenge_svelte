<script>
    import Teams from './Teams.svelte';

    let redTeam = 'red'
    let blueTeam = 'blue';
    let redValues = 20
    let blueValues = 20

    const resetValues = () => {
        redValues = 20;
        blueValues = 20;
    }

</script>

<main class="container">
    <div class="row">
        <div class="column">
            <h1>MTG Counter App</h1>
        </div>
    </div>
    <div class="row">
        <div class="column">
            <Teams color={redTeam} bind:value={redValues}/>
        </div>
        <div class="column">
            <Teams color={blueTeam} bind:value={blueValues}/>
        </div>
    </div>
    <div style="text-align: center">
        {#if blueValues === 0}
            <h2 style="color: {redTeam}">Red Team Wins</h2>
        {:else if redValues === 0}
                <h2 style="color: {blueTeam}">Blue Team Wins</h2>
        {/if}
        {#if redValues === 0 || blueValues === 0}
            <button style="background: green" on:click={resetValues}>New Game</button>
            {:else}
            <button on:click={resetValues}>Reset Game</button>
        {/if}
    </div>
</main>


<style>
    h1 {
        color: black;
        font-size: 3rem;
        font-weight: 500;
        text-align: center;
        line-height: none;
    }
    button {
        background-color: orange;
        border: none;
        margin-top: .5rem;
        width: 100%;
    }

</style>