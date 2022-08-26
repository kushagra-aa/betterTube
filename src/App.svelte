<svelte:head>
	<link rel="stylesheet" href="https://unpkg.com/mono-icons@1.0.5/iconfont/icons.css" >
</svelte:head>

<script>
    import Main from './lib/Main.svelte';
    import Nav from './lib/Nav.svelte'
    import SideBar from './lib/SideBar.svelte'
</script>

<Nav/>
<main>
  <SideBar/>
  <div class="container">
    <Main/>
  </div>
</main>