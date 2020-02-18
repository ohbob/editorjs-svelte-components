<script>
    import header from './editorjsComponents/Header.svelte';
    import paragraph from './editorjsComponents/Paragraph.svelte';
    import image from './editorjsComponents/Image.svelte';
    import quote from './editorjsComponents/Quote.svelte';
    import list from './editorjsComponents/List.svelte';
    import delimiter from './editorjsComponents/Delimiter.svelte';
    import checklist from './editorjsComponents/Checklist.svelte';
    import embed from './editorjsComponents/Embed.svelte';

    const components = {header, paragraph, image, quote, list, delimiter, checklist, embed};

    async function getData() {
        const res = await fetch('http://localhost:1337/posts');
        return await res.json();
    }
</script>

<div class="container">
{#await getData()}
    <p>loading.....</p>
{:then blogpost}
    {#each blogpost.reverse() as article}
        <article>
            {#each JSON.parse(article.content).blocks as block}
                <svelte:component this={components[block.type]} data={block}/>
            {/each}
        </article>
    {/each}
{/await}
</div>

<style>
    .container{
        padding:40px;
    }
</style>