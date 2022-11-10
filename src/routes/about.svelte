<script context="module">
  import { browser, dev } from "$app/env";

  // we don't need any JS on this page, though we'll load
  // it in dev so that we get hot module replacement...
  export const hydrate = dev;

  // ...but if the client-side router is already loaded
  // (i.e. we came here from elsewhere in the app), use it
  export const router = browser;

  // since there's no dynamic data here, we can prerender
  // it so that it gets served as a static asset in prod
  export const prerender = true;
</script>

<svelte:head>
  <title>About</title>
  <meta name="description" content="About" />
</svelte:head>

<article class="content">
  <section>
    <h2 class="Title">About The Author</h2>
    <section>
      <h4 class="Subtitle">Ahmad al-Zahid</h4>
      <p>
        Ahmad al-Zahid's fullname is Abu l-'Abbas Ahmad bin Sulayman al-Zahid
      </p>
    </section>
  </section>
  <section>
    <h2>About The Book</h2>
    <section><h4>al-Sittin Mas'alah</h4></section>
  </section>
</article>

<style>
  article {
    height: inherit;
    display: flex;
    flex-direction: column;
  }
</style>
