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
</div>

<style>
  .layout-wrapper {
    display: grid;
    grid-template-columns: 1fr 3fr;
    grid-template-rows: 50px 1fr;
    grid-template-areas:
      "header header"
      "side main";
  }

  main {
    display: flex;
    grid-area: main;
    overflow-y: auto;
  }

  .main-section-container {
    width: 100%;
  }

  @media (max-width: 640px) {
    .layout-wrapper {
      grid-template-columns: 1fr;
      grid-template-rows: 50px 130px 1fr;
      grid-template-areas:
        "header"
        "side"
        "main";
    }
  }
</style>
