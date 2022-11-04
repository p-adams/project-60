<script>
  import Header from "$lib/header/Header.svelte";

  import "../app.css";
</script>

<div class="layout-wrapper">
  <Header />

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
    grid-template-rows: 75px 500px 20px;
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
  }

  @media (min-width: 480px) {
    footer {
      padding: 40px 0;
    }
  }
</style>
