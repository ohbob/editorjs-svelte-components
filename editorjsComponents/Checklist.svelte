<script>
    export let data = '';

    const items = data.data.items;
</script>

{#if items}
    <form>
        {#each items as {text, checked}}
            <input type="checkbox" id={text} name={text} value={text} checked={checked}>
            <label for="{text}">{text}</label><br>
        {/each}
    </form>
{/if}

