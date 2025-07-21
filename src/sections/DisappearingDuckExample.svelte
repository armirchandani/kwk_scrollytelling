<script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div style="display: flex; gap: 2rem; align-items: flex-start;">
  <!-- Left: Text scrollytelling -->
  <div style="flex: 1;">
    <Scroller layout="left">
      {#snippet sticky()}
        <div>
          <img
            class="avg-img"
            src="female&male.png"
            alt="Average Interest Rate for Black or African American Applicants Female vs Male"
            in:fly={{ y: 200, duration: 2000 }}
            out:fade
          />
          <br />
        </div>
         <div>
  <p>
    While the difference is modest, females tend to receive slightly higher interest rates on housing loans, averaging <strong>5.14%</strong> compared to <strong>5.11%</strong> for males.
  </p>
</div>

      {/snippet}

      {#snippet scrolly()}
        <ArticleText>
  While the difference is modest, females tend to receive slightly higher interest rates on housing loans, averaging <strong>5.14%</strong> compared to <strong>5.11%</strong> for males. This subtle gap can accumulate over the lifetime of a loan, potentially affecting long-term affordability and wealth accumulation.
</ArticleText>

<ArticleText>
  <strong>Sources:</strong><br />
  - <a href="https://github.com/armirchandani/AvgInterestRates" target="_blank">GitHub: Average Interest Rates Data</a><br />
  - <a href="https://blackwealthdata.org/explore/homeownership#HOM-01" target="_blank">Black Wealth Data Center: Homeownership Overview</a><br />
  These sources provide valuable insights into racial disparities in homeownership, lending practices, and financial outcomes across the U.S., with a focus on Black communities.
</ArticleText>

<ArticleText>
  <strong>SWOT Analysis: Black Homeownership in Miami-Dade County</strong><br /><br />
  <u>Strengths:</u><br />
  • Strong community networks and cultural resilience<br />
  • Increased awareness of housing inequities<br />
  • Access to public datasets for policy advocacy<br /><br />
  
  <u>Weaknesses:</u><br />
  • High rent burden (37.5%)<br />
  • Elevated interest rates for Black borrowers (18.1% above 6.77%)<br />
  • Limited access to affordable financing<br /><br />
  
  <u>Opportunities:</u><br />
  • Expansion of affordable housing initiatives<br />
  • Community-led development and investment<br />
  • Financial literacy and homeownership programs<br /><br />
  
  <u>Threats:</u><br />
  • Economic instability and high social vulnerability<br />
  • Gentrification pressures<br />
  • Continued bias in lending and housing markets
</ArticleText>

      {/snippet}
    </Scroller>
  </div>
</div>

<style>
  .avg-img {
    width: 90%;
    max-width: 800px;
    display: block;
    margin: 2rem auto;
    border-radius: 12px;
box-shadow: 0 6px 16px rgba(0, 0, 0, 0.25);
  }
</style>
