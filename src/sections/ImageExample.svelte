<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <img class="house-img" src="miami_dade.jpeg" alt="Miami-Dade House"/>
        {/snippet}

        {#snippet scrolly()}
         <ArticleText>
    While rent burden and income levels give us a snapshot of affordability, there's another critical factor that impacts long-term housing opportunities, such as loan interest rates.
</ArticleText>

<ArticleText>
    Access to favorable financing can determine whether a family is able to purchase a home or remain stuck in the rental cycle. Unfortunately, interest rates aren’t experienced equally across racial and ethnic groups.
</ArticleText>

<ArticleText>
    Let us now examine the average interest rates paid on home loans by race and ethnicity to better understand the financial disparities in borrowing.
</ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
     .house-img {
        width: 90%;         /* Make image take more horizontal space */
        max-width: 800px;   /* Optional: prevent it from becoming too large on big screens */
        display: block;
        margin: 2rem auto;  /* Add spacing */
        border-radius: 12px;
        box-shadow: 0 6px 16px rgba(0, 0, 0, 0.25);
    }
</style>


