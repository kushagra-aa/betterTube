<script>
    export let content;
    export let title;
    export let Icon;
</script>
<div class="feature-container">
<img src={Icon} alt=''/>
<h4>{title}</h4>
<p>{content}</p>
</div>