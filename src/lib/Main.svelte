<script>
import HeroIcon from './../assets/home-bg.png';
import About from './About.svelte';
</script>

<div class='hero-container'>
    <div class="title">
        <h2>Welcome To</h2>
        <h1>Better<div>T</div>ube</h1>
    </div>
    <img src={HeroIcon} alt="" class="hero-icon">
    <div class="hero-buttons-container">
        <button>start watching</button>
        <button>explore more</button>
    </div>
</div>
<About/>