<script>
  import { onMount } from "svelte";
import Footer from "./lib/Footer.svelte";
  import Main from "./lib/Main.svelte";
  import Nav from "./lib/Nav.svelte";
  import SideBar from "./lib/SideBar.svelte";
  let isSidebarCollapsed = false;
  let isNavbarHidden = false;
  let minScroll = 10;
  let scrollY=0;
  let lastScroll;
  onMount(() => {
    lastScroll = scrollY;
    console.log("--------<Function:OnMount>--------");
    console.log("lastScroll :>> ", lastScroll);
    console.log("--------<Function:OnMount:End>--------");
  });
  $: if (scrollY-minScroll>lastScroll) {
    isNavbarHidden = true;
    lastScroll = scrollY;
    console.log("--------<Function:hidescroll>--------");
    console.log("Last:>>", lastScroll);
    console.log("Scroll:>>", scrollY);
    console.log("--------<Function:hidescroll:End>--------");
  }
  $: if (scrollY < lastScroll-minScroll) {
    isNavbarHidden = false;
    lastScroll = scrollY;
    console.log("--------<Function:showscroll>--------");
    console.log("Last:>>", lastScroll);
    console.log("Scroll:>>", scrollY);
    console.log("--------<Function:showscroll:End>--------");
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
<Footer bind:isSidebarCollapsed={isSidebarCollapsed}/>