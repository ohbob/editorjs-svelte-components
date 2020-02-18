<script>
    export let data = '';

    const cite = data.data.caption;
    const quote = data.data.text;

    // "alignment":"left" or "alignment":"center"}

</script>

{#if quote}
    <blockquote cite={cite}>
        {quote}
    </blockquote>
{/if}


<style>
    blockquote {
        display: block;
        border-width: 2px 0;
        border-style: solid;
        border-color: #eee;
        padding: 1.5em 0 0.5em;
        margin: 1.5em 0;
        position: relative;
    }

    blockquote:before {
        content: '\201C';
        position: absolute;
        top: 0em;
        left: 50%;
        transform: translate(-50%, -50%);
        background: transparent;
        width: 3rem;
        height: 2rem;
        font: 6em/1.08em 'PT Sans', sans-serif;
        color: #666;
        text-align: center;
    }

    blockquote:after {
        content: "\2013 \2003" attr(cite);
        display: block;
        text-align: right;
        font-size: 0.875em;
        color: #e74c3c;
    }
</style>