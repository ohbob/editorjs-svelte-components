<script>
    export let data = '';

    const text = data.data.text;
</script>

{#if text}
    <p>{@html text}</p>
{/if}


<style>
    :global(p a) {
        color: blue;
    }
</style>