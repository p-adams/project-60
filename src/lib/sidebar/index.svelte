<script>
  import { chapters } from "../../routes/chapters";
  /**
   * @param {{ preventDefault: () => void; currentTarget: HTMLAnchorElement; }} event : Event
   */
  function handleAnchorClick(event) {
    event.preventDefault();
    const link = event.currentTarget;
    const anchorId = new URL(link.href).hash.replace("#", "");
    const anchor = document.getElementById(anchorId);
    window.scrollTo({
      top: anchor?.offsetTop,
      behavior: "smooth",
    });
  }
</script>

<aside>
  <nav>
    <ul class="nav">
      {#each chapters as chapter}
        <li>
          <a href="#{chapter.anchor}" on:click={handleAnchorClick}
            >{chapter.title}</a
          >
        </li>
      {/each}
    </ul>
  </nav>
</aside>

<style>
  aside {
    grid-area: side;
  }
  aside nav ul {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
  @media (min-width: 640px) {
    aside {
      position: fixed;
      margin-top: 50px;
      height: 100%;
      overflow-y: auto;
    }
    aside nav ul {
      display: flex;
      flex-direction: column;
    }
  }
</style>
