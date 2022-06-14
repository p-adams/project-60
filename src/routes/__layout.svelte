<script>
  import Header from "$lib/header/Header.svelte";
  import Sidenav from "$lib/sidenav/Sidenav.svelte";
  import "../app.css";
</script>

<div class="layout-wrapper">
  <Header />
  <Sidenav />

  <main>
    <slot />
  </main>

  <footer class="footer-wrapper">
    <p>
      visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to learn SvelteKit
    </p>
  </footer>
</div>

<style>
  .layout-wrapper {
    height: 100vh;
    display: grid;
    grid-template-columns: 300px 1fr;
    grid-template-areas:
      "header-wrapper header-wrapper"
      "sidenav-wrapper main"
      "footer-wrapper footer-wrapper";

    gap: 10px;
  }

  main {
    border: 1px solid green;
    grid-area: main;
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 1rem;
    width: 100%;
    max-width: 1024px;
    margin: 0 auto;
    box-sizing: border-box;
  }

  footer {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 40px;
  }

  footer a {
    font-weight: bold;
  }

  @media (min-width: 480px) {
    footer {
      padding: 40px 0;
    }
  }
</style>
