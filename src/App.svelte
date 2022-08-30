<svelte:head>
	<link rel="stylesheet" href="https://unpkg.com/mono-icons@1.0.5/iconfont/icons.css" >
</svelte:head>

<script>
    import Main from './lib/Main.svelte';
    import Nav from './lib/Nav.svelte'
    import SideBar from './lib/SideBar.svelte'
    let isSidebarCollapsed=false;
    let isNavbarHidden=false;
    let minScroll=80;
    let scrollY=0;
    let lastScroll=scrollY
    $:if(scrollY>lastScroll){
      lastScroll=scrollY;
      console.log('========',lastScroll)
    }
    $:if(scrollY>minScroll){
      isNavbarHidden=true;

    }
    $:if(scrollY<lastScroll){isNavbarHidden=false;lastScroll=scrollY}
</script>
<svelte:window bind:scrollY={scrollY}/>
<Nav bind:isSidebarCollapsed bind:isNavbarHidden/>
<main class={`${isNavbarHidden&&'hidden-navbar'}`}>
  <SideBar bind:isSidebarCollapsed bind:isNavbarHidden/>
  <div class={`container ${isSidebarCollapsed&&'collapsed-sidebar'} ${isNavbarHidden&&'hidden-navbar'}`}>
    <Main/>
  </div>
</main>