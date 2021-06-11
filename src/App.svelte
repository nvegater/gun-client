<script lang="ts">
    export let someNumber: number;

    export let displayNumber: string = "0"

    const startingNumber = "....L:-)...."

    export const formatNumber =
        (num: number): string =>
            num !== null && num !== undefined
                ? num.toString()
                : startingNumber

    $: displayNumber = formatNumber(someNumber); // format on change

</script>

<main>
    <h2>Show me the display number: { displayNumber }</h2>
    {#if (someNumber === null)}
        <p style="color: red">Invalid number</p>
    {/if}
    <label>Change the number</label>
    <input type="number" bind:value={someNumber} />
</main>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }

    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    h2 {
        color: chocolate;
        font-weight: lighter;
    }

    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }

    label {
        color: cadetblue;
        text-align: left;
        margin: 1em 0 1em 0;
    }
</style>