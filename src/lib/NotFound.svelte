<script>
  import { Link } from "svelte-navigator";
  import Not from "./../assets/404-image.jpg";
</script>

<section class="not-found">
  <img src={Not} alt="oops" />
  <Link to="/">Get back home</Link>
</section>
