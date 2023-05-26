<script>
  import AppHeader from "$lib/header/Appheader.svelte";

  import "../app.css";
</script>

<div class="layout-wrapper">
  <AppHeader />

  <main>
    <div class="main-section-container">
      <slot />
    </div>
  </main>

  <footer class="footer-wrapper">
    <p>footer</p>
  </footer>
</div>

<style>
  .layout-wrapper {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 75px 560px 20px;
    grid-template-areas:
      "header-wrapper"
      "main"
      "footer-wrapper";
    gap: 10px;
  }

  main {
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

  .main-section-container {
    width: 100%;
    height: 100%;
  }

  .footer-wrapper {
    grid-area: footer-wrapper;
    border: 1px solid red;
  }

  footer {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    align-self: flex-end;
  }
</style>
