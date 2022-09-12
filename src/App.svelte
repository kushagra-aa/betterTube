<script>
  import { Router, Route, Link } from "svelte-navigator";
  import { onMount } from "svelte";
  import Footer from "./lib/Footer.svelte";
  import Main from "./lib/Main.svelte";
  import Nav from "./lib/Nav.svelte";
  import SideBar from "./lib/SideBar.svelte";
  import NotFound from "./lib/NotFound.svelte";
  let isSidebarCollapsed = false;
  let isNavbarHidden = false;
  let minScroll = 10;
  let scrollY = 0;
  let lastScroll;
  onMount(() => {
    lastScroll = scrollY;
    console.log("--------<Function:OnMount>--------");
    console.log("lastScroll :>> ", lastScroll);
    console.log("--------<Function:OnMount:End>--------");
  });
  $: if (scrollY - minScroll > lastScroll) {
    isNavbarHidden = true;
    lastScroll = scrollY;
    console.log("--------<Function:hidescroll>--------");
    console.log("Last:>>", lastScroll);
    console.log("Scroll:>>", scrollY);
    console.log("--------<Function:hidescroll:End>--------");
  }
  $: if (scrollY < lastScroll - minScroll) {
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
<Router>
  <Nav bind:isSidebarCollapsed bind:isNavbarHidden />
  <main class={`${isNavbarHidden && "hidden-navbar"}`}>
    <SideBar bind:isSidebarCollapsed bind:isNavbarHidden />
    <div
      class={`container ${isSidebarCollapsed && "collapsed-sidebar"} ${
        isNavbarHidden && "hidden-navbar"
      }`}
    >
      <Route path="/">
        <Main />
      </Route>
      <Route path="/home">
        <Main />
      </Route>
      <Route path="">
        <NotFound />
      </Route>
    </div>
  </main>
  <Footer bind:isSidebarCollapsed />
</Router>
