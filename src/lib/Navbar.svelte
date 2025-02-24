<script>
  import { page } from "$app/stores";
  import { derived } from "svelte/store";

  const currentPath = derived(page, ($page) => $page.url?.pathname || "/");
</script>

<nav>
  <div>
    <img src={"/data/images/emptycup-logo.png"} alt="logo">
  </div>
  <a href="/" class={$currentPath === "/" ? "active" : ""}>Home</a>
  <a href="/speakers" class={$currentPath === "/speakers" ? "active" : ""}>Speakers</a>
  <a href="/schedule" class={$currentPath === "/schedule" ? "active" : ""}>Schedule</a>
  <a href="/sponsors" class={$currentPath === "/sponsors" ? "active" : ""}>Sponsors</a>
  <a href="/about" class={$currentPath === "/about" ? "active" : ""}>About</a>
  <a href="/contact" class={$currentPath === "/contact" ? "active" : ""}>Contact</a>
</nav>

<style>
  nav {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 35px;
    height: 100px;
    background: white;
  }

  a {
    font-size: 20px;
    color: black;
    font-weight: 550;
    text-decoration: none;
    transition: all ease-in-out 100ms;
    padding-bottom: 5px;
  }

  a:hover {
    color: orange;
    border-bottom: 5px solid orangered;
  }

  .active {
    color: orange;
  }
  @media screen and (max-width:720px){
    nav{
      display: none;
    }
	}
</style>
