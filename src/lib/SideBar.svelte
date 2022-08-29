<script>
export let isSidebarCollapsed=false;
</script>

<div class={`sidebar ${isSidebarCollapsed&&'collapsed-sidebar'}`}>
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
</div>