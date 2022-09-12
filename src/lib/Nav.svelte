<script>
import { Link } from "svelte-navigator";


export let isSidebarCollapsed=false
export let isNavbarHidden=false
const collapseSidebar=()=>{
    isSidebarCollapsed=!isSidebarCollapsed;
}
</script>

<nav class={`${isNavbarHidden&&'hidden-navbar'}`}>
    <div class="nav-item nav-ham" on:click={collapseSidebar}>
        <i class={`mi ${!isSidebarCollapsed?'mi-close':'mi-menu'}`}></i>
    </div>
    <Link to='/' class="nav-item logo">Better
        <span>T</span>
        ube</Link>
    <Link to='/' class="nav-item">home</Link>
    <Link to='/services' class="nav-item">servies</Link>
    <Link to='/contact' class="nav-item">contact</Link>
    <Link to='/about' class="nav-item">about</Link>
    <div class="nav-item search">
        <input type="text" placeholder="Search..."/>
    </div>
</nav>