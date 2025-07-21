<script>
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import TitleCard from "../lib/TitleCard.svelte";
  import { onMount } from "svelte";
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <img class="percent-img" src="percent_of_Income_Spent_on_Rent .png" alt="Percent of Income Spent on Rent by Black communities" />
            <div>
                <p>
                    Black households in <strong>Miami-Dade County</strong> spend a significant portion of their income on rent,
          with <strong>37.5%</strong> of income going toward housing costs.
                </p>
                <p>
                     This high rent burden can make it difficult to save for a down payment on a home,
          limiting opportunities for homeownership and long-term wealth building.
                </p>
                <p>
                     <strong>Source:</strong>
          <a href="https://blackwealthdata.org/explore/homeownership#HOM-09" target="_blank"> 
            Black Wealth Data Center (BWDC)
            </a>
                </p>
            </div>
        {/snippet}

        {#snippet scrolly()}
  <ArticleText>
    <strong>Welcome to my data scrollytelling piece on Miami-Dade County.</strong>
  </ArticleText>

  <ArticleText>
    In this project, we will explore the structural and financial challenges that Black households face on the path to homeownership. 
    From high interest rates to limited income and disproportionate rent burdens, this piece highlights key data points to tell a deeper story.
  </ArticleText>

  <ArticleText>
    Alongside this text, you will see a visual showing that the median income for Black residents in Miami-Dade County is <strong>$51,550</strong>.
    In 2023, they spent <strong>37.5%</strong> of that income on rent alone being a substantial burden that makes saving for a down payment increasingly difficult.
  </ArticleText>

  <ArticleText>
    <strong>
      As you scroll, reflect on how these factors compound and contribute to inequities in homeownership access across the country.
    </strong>
  </ArticleText>
{/snippet}
    </Scroller>
</div>

<style>
  .percent-img {
    width: 100%;
    height: auto;
    display: block;
    margin: 0 auto;
  }
</style>
