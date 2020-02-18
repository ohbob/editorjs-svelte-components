<script>
    export let data = '';

    const text = data.data.text;
    const level = data.data.level;
    const headerTypes = {
        '1': 'h1',
        '2': 'h2',
        '3': 'h3',
        '4': 'h4',
        '5': 'h5',
        '6': 'h6',
    };

    function render_block() {
        let tag = headerTypes[level];
        return `<${tag}>${text}</${tag}`;
    }
</script>

{#if text}
    {@html render_block()}
{/if}
