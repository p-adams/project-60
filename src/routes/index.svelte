<script context="module">
  export const prerender = true;
</script>

<script>
  import TextChapter from "../routes/chapters/index.svelte";
</script>

<svelte:head>
  <title>Project 60</title>
  <meta name="description" content="Project 60" />
</svelte:head>

<article>
  <TextChapter />
</article>

<style>
  article {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 1;
  }
</style>
