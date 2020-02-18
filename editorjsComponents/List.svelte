<script>
    export let data = '';

    const style = data.data.style;
    const listItems = data.data.items;
</script>
{#if listItems}
    {#if style === "ordered"}
        <ol>
            {#each listItems as item}
                <li>{item}</li>
            {/each}
        </ol>
    {:else if style === "unordered"}
        <ul>
            {#each listItems as item}
                <li>{item}</li>
            {/each}
        </ul>
    {/if}
{/if}