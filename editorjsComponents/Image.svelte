<script>
    export let data = '';

    const file = data.data.file;
    const url = data.data.file.url;
    const caption = data.data.caption;

    //    "data":{"
    //    file":{"url":"http://localhost:1337/uploads/70dbe95620b040d4ae23a0ca0e6b6a2e.jpg"},
    //    "caption":"",
    //    "withBorder":false,
    //    "stretched":false,
    //    "withBackground":false}
    //    }

</script>

{#if file}
    <figure>
        <img src="{url}" alt="{caption}">
        {#if caption}
            <figcaption>
                {caption}
            </figcaption>
        {/if}
    </figure>
{/if}