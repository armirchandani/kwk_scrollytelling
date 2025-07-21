<script>
    let { children } = $props();
</script>

<div class="article-text">
    <p>
        {@render children()}
    </p>
</div>

<style>
    .article-text {
        margin: 50vh auto;
        width: 50%;
        background-color: #ffffff;
        color: #1e1e1e;
        border: solid #2563eb 3px;
        border-radius: 20px;
        padding: 20px;
        box-shadow: 16px 16px #cbd5e1;
    }
</style>
