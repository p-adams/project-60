<script>
  import AppSidebar from "$lib/AppSidebar.svelte";
  import AppHeader from "$lib/header/AppHeader.svelte";

  import "../app.css";
</script>

<div class="layout-wrapper">
  <AppHeader />
  <AppSidebar />

  <main>
    <div class="main-section-container">
      <slot />
    </div>
  </main>
  <footer>
    <div>footer</div>
  </footer>
</div>

<style>
  .layout-wrapper {
    display: grid;
    grid-template-columns: 1fr 3fr;
    grid-template-rows: 1fr 550px 1fr;
    grid-template-areas:
      "header header"
      "side main"
      "footer footer";
  }

  main {
    display: flex;
    grid-area: main;
  }

  .main-section-container {
    width: 100%;
  }

  footer {
    grid-area: footer;
  }
  footer div {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    align-self: flex-end;
  }
  @media (max-width: 640px) {
    .layout-wrapper {
      grid-template-columns: 1fr;
      grid-template-rows: 1fr 1fr 5fr 1fr;
      grid-template-areas:
        "header"
        "side"
        "main"
        "footer";
    }
  }
</style>
