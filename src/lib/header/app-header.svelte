<script>
  import { page } from "$app/stores";
</script>

<header class="header-wrapper">
  <div class="header-items">
    <div class="corner">
      <a href="https://github.com/p-adams/project-60" target="_blank">
        Project 60
      </a>
    </div>

    <nav>
      <ul>
        <li class:active={$page.url.pathname === "/"}>
          <a sveltekit:prefetch href="/">Home</a>
        </li>
        <li class:active={$page.url.pathname === "/about"}>
          <a sveltekit:prefetch href="/about">About</a>
        </li>
      </ul>
    </nav>

    <div class="corner">
      <!-- TODO put something else here? github link? -->
      <a href="https://github.com/p-adams/project-60" target="_blank">
        <img class="github-link-img" src="github.png" alt="GitHub Link" />
      </a>
    </div>
  </div>
</header>

<style>
  .header-wrapper {
    background-color: #f7fafc;
  }
  .header-items {
    display: grid;
    grid-template-columns: 100px 1fr 100px;
    grid-area: header-wrapper;
    padding: 6px;
    margin-left: 12px;
    margin-right: 12px;
  }

  .corner {
    /*width: 5em;*/
    height: 3em;
  }

  .corner a {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    color: var(--heading-color);
    font-size: larger;
  }

  .github-link-img {
    width: 24px;
    height: 24px;
  }

  nav {
    display: flex;
    justify-content: center;
    --background: rgba(255, 255, 255, 0.7);
  }

  ul {
    position: relative;
    padding: 0;
    margin: 0;
    height: 3em;
    display: flex;
    justify-content: center;
    align-items: center;
    list-style: none;
    background: var(--background);
    background-size: contain;
  }

  li {
    position: relative;
    height: 100%;
  }

  li.active {
    border-bottom: 1px solid var(--heading-color);
  }

  nav a {
    display: flex;
    height: 100%;
    align-items: center;
    padding: 0 1em;
    color: var(--heading-color);
    font-weight: 700;
    font-size: 0.8rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    text-decoration: none;
    transition: color 0.2s linear;
  }

  a:hover {
    color: var(--accent-color);
  }
</style>
