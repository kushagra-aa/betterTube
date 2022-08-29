<script>
export let isSidebarCollapsed=false
const collapseSidebar=()=>{
    isSidebarCollapsed=!isSidebarCollapsed;
}
</script>

<nav>
    <div class="nav-item nav-ham" on:click={collapseSidebar}>
        <i class="mi mi-menu"></i>
    </div>
    <div class="nav-item logo">Better
        <span>T</span>
        ube</div>
    <div class="nav-item">home</div>
    <div class="nav-item">servies</div>
    <div class="nav-item">contact</div>
    <div class="nav-item">about</div>
    <div class="nav-item search">
        <input type="text" placeholder="Search..."/>
    </div>
</nav>