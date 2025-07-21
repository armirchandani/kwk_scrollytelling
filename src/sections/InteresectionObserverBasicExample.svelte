<script>
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    // this `options` object below is passed into the <ObservedArticleText>
    // component, and from there it gets passed to the IntersectionObserver object w
    // when it's created.
    // the thresholds to fire the callback are 85% and 95%. in the callback function,
    // we check whether the visible area is >= 90%. so, triggering the callback at
    // 85% and 95% ensures we trigger the correct change in background color
    // whether the element is being scrolled into the viewport or out of the viewport.
    const options = {
        threshold: [0.8, 0.9],
    };

    const callback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#e3ff00";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#888888";
            }
        });
    };
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div class="percentage-text">
                <img src="percentage_interest.png" alt="Percentage of Housing Loans with Interest Rates more than 6.77%" style="width: 70%; height: auto;" />
            </div>
            <div>
                <p>
                    A notable percentage (<strong>18.1%</strong>) of housing loans for Black or African American individuals have interest rates above <strong>6.77%</strong>.
                </p>
            </div>

        {/snippet}
{#snippet scrolly()}
    <ArticleText>
        A notable percentage (<strong>18.1%</strong>) of housing loans for Black or African American individuals have interest rates above <strong>6.77%</strong>, 
        highlighting disparities in borrowing costs that can impact long-term wealth building.
    </ArticleText>

    <ArticleText>
        This analysis underscores the challenges faced by Black borrowers in accessing affordable financing, which may contribute to ongoing inequities in homeownership rates.
    </ArticleText>

    <ArticleText>
        Sources: <a href="https://blackwealthdata.org/explore/homeownership#HOM-01" target="_blank" rel="noopener noreferrer">BWDC</a> and <a href="https://github.com/armirchandani/AvgInterestRates" target="_blank" rel="noopener noreferrer">GitHub Data Repository</a>.
    </ArticleText>
{/snippet}
    </Scroller>
</div>

<style>
    .percentage-text {
        text-align: center;
        font-size: 1.2em;
        color: #333;
        margin-bottom: 1rem;
    }
    </style>