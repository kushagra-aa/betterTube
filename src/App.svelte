<svelte:head>
	<link rel="stylesheet" href="https://unpkg.com/mono-icons@1.0.5/iconfont/icons.css" >
</svelte:head>

<script>
    import Main from './lib/Main.svelte';
    import Nav from './lib/Nav.svelte'
    import SideBar from './lib/SideBar.svelte'
    let isSidebarCollapsed=false;
</script>

<Nav bind:isSidebarCollapsed/>
<main>
  <SideBar bind:isSidebarCollapsed/>
  <div class={`container ${isSidebarCollapsed&&'collapsed-sidebar'}`}>
    <Main/>
  </div>
</main>