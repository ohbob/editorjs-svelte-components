<script>
    export let data = '';

    const service = data.data.service;
    const source = data.data.service;
    const embed = data.data.embed;
    const caption = data.data.caption;
</script>

{#if service === "youtube"}
    <iframe
            width=100%
            height=400px
            src={embed}
            frameborder="0"
            allow="autoplay; encrypted-media"
            allowfullscreen>
    </iframe>
{/if}

