<script>
  import AppHeader from "$lib/header/Appheader.svelte";

  import "../app.css";
</script>

<div class="layout-wrapper">
  <AppHeader />

  <main>
    <ul class="nav">
      <li>a</li>
      <li>b</li>
      <li>c</li>
    </ul>
    <div class="main-section-container">
      <slot />
    </div>
  </main>
  <footer>
    <p>footer</p>
  </footer>
</div>

<style>
  .layout-wrapper {
    display: flex;
    flex-direction: column;
  }

  main {
    display: flex;
    width: 100%;
    height: calc(100vh - 120px);
    margin: 0 auto;
    box-sizing: border-box;
    outline: 1px solid red;
  }

  .nav {
    width: 170px;
  }

  .main-section-container {
    width: 100%;
  }

  footer {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    align-self: flex-end;
  }
</style>
