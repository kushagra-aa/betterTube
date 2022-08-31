<script>
  import { onMount } from "svelte";
  import Main from "./lib/Main.svelte";
  import Nav from "./lib/Nav.svelte";
  import SideBar from "./lib/SideBar.svelte";
  let isSidebarCollapsed = false;
  let isNavbarHidden = false;
  let minScroll = 80;
  let scrollY = 0;
  let lastScroll;
  onMount(() => {
    lastScroll = scrollY;
    console.log('lastScroll :>> ', lastScroll);
  });
  $: if (scrollY > lastScroll) {
    lastScroll = scrollY;
    console.log("Last In scroll>last========", lastScroll);
    console.log("Scroll In scroll>last========", lastScroll);
  }
  $: if (scrollY > minScroll) {
    isNavbarHidden = true;
    console.log("Last In scroll>min========", lastScroll);
    console.log("Scroll In scroll>min========", scrollY);
  }
  $: if (scrollY < lastScroll) {
    isNavbarHidden = false;
    lastScroll = scrollY;
    console.log("Last In scroll<lastScroll========", lastScroll);
    console.log("Scroll In scroll<lastScroll========", scrollY);
  }
</script>

<svelte:head>
  <link
    rel="stylesheet"
    href="https://unpkg.com/mono-icons@1.0.5/iconfont/icons.css"
  />
</svelte:head>
<svelte:window bind:scrollY />
<Nav bind:isSidebarCollapsed bind:isNavbarHidden />
<main class={`${isNavbarHidden && "hidden-navbar"}`}>
  <SideBar bind:isSidebarCollapsed bind:isNavbarHidden />
  <div
    class={`container ${isSidebarCollapsed && "collapsed-sidebar"} ${
      isNavbarHidden && "hidden-navbar"
    }`}
  >
    <Main />
  </div>
</main>
