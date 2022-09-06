<script>
export let isSidebarCollapsed=false;
export let isNavbarHidden=false;
</script>

<div class={`sidebar ${isSidebarCollapsed&&'collapsed-sidebar'} ${isNavbarHidden&&'hidden-navbar'}`}>
    <div class="sidebar-item">
        <i class="mi mi-play"></i>
        <p>Videos</p>
    </div>
    <div class="sidebar-item">
        <i class="mi mi-map"></i>
        <p>Explore</p>
    </div>
    <div class="sidebar-item">
        <i class="mi mi-archive"></i>
        <p>Library</p>
    </div>
    <div class="sidebar-item">
        <i class="mi mi-clock"></i>
        <p>History</p>
    </div>
    <div class="sidebar-item">
        <i class="mi mi-heart"></i>
        <p>Likes</p>
    </div>
    <div class="sidebar-item">
        <i class="mi mi-add"></i>
        <p>WatchLater</p>
    </div>
    <div class="sidebar-item">
        <i class="mi mi-settings"></i>
        <p>Settings</p>
    </div>
    <div class="sidebar-item">
        <i class="mi mi-delete"></i>
        <p>deleted</p>
    </div>
    <div class="sidebar-item">
        <i class="mi mi-camera"></i>
        <p>create</p>
    </div>
    <div class="sidebar-item">
        <i class="mi mi-chevron-down"></i>
        <p>More</p>
    </div>
</div>