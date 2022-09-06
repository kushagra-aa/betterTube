<script>
import Feature from "./Feature.svelte";
import Plays from "./../assets/plays-everything.svg";
import Easy from "./../assets/easy-to-style.svg";
import Plugins from "./../assets/100s-of-plugins.svg";
import Support from "./../assets/supported-everywhere.svg";
let features=[
  {
    'icon':Plays,
    'content':`Plays “traditional” file formats such as MP4 and WebM, but also supports adaptive streaming formats such as HLS and DASH. There’s even a special UI for live streams!`,
    'title':`Plays anything`
  },
  {
    'icon':Easy,
    'content':`Video.js is designed to be a reliable and consistent base to build on top of. The player looks great out of the box, but can be easily styled with a little bit of extra CSS.`,
    'title':`Easy to style`
  },
  {
    'icon':Plugins,
    'content':`When you need to add additional functionality, a well-documented plugin architecture has your back. The community has already built`,
    'title':`100s of plugins`
  },
  {
    'icon':Support,
    'content':`Your video should work everywhere your app does. The team makes an effort to support every modern browser we can, including desktop and mobile.`,
    'title':`Supported everywhere`
  },
]

</script>

<section class="features-container">
  <h3>our best features</h3>
  <p>
    BetteTube is a web video player built from the ground up by SvelteJS. It
    supports modern streaming formats, as well as YouTube, Vimeo, and even Flash
    (through plugins, more on that later).
  </p>

  <p>
    It supports video playback on desktop and mobile devices. The project was
    started mid 2022, and now has hundreds of contributors and is used on over
    45,000 websites.
  </p>
  <div class="features-grid">
    {#each features as feature}
  <Feature content={feature.content} title={feature.title} Icon={feature.icon}/>
    {/each}
  </div>
</section>
