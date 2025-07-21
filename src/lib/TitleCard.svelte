<script>
    let { title, subtitle } = $props();
</script>

<div class="title-card">
    <div class="content">
        <h1>{title}</h1>
        <p>{subtitle}</p>
    </div>
</div>

<style>
    .title-card {
        background-color: #e6f2ec; /* soft sage green */
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 3rem 1.5rem;
        box-sizing: border-box;
        font-family: "Inter", sans-serif;
    }

    .content {
        max-width: 700px;
        background-color: #ffffff; /* clean white card */
        padding: 2.5rem;
        border: 5px solid #8a4ebf; /* muted plum border */
        border-radius: 2rem;
        box-shadow: 12px 12px 0 #c3d7cc; /* soft shadow for depth */
    }

    h1 {
        font-size: 3rem;
        margin: 0;
        color: #3a3a3a; /* deep charcoal */
        text-shadow: 1px 1px 0 #d2f2e0;
    }

    p {
        font-size: 1.3rem;
        color: #555;
        margin-top: 1.2rem;
        line-height: 1.6;
    }

    @media (max-width: 600px) {
        h1 {
            font-size: 2.2rem;
        }

        p {
            font-size: 1.1rem;
        }
    }
</style>

