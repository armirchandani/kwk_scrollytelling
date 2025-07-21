<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import {Chart} from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    let options = {
        chart: {
            type: "pie",
            backgroundColor: "#e3ff00",
            borderColor: "#007052",
            borderWidth: 5,
            borderRadius: 20,
        },
        title: {
            text: "Median Income by Race – Miami-Dade (2023)",
        },
        subtitle: {
            text: "Based on 2023 U.S. Census ACS Data",
        },
        plotOptions: {
            pie: {
                allowPointSelect: true,
                dataLabels: [
                    {
                        enabled: true,
                        distance: 20,
                    },
                    {
                        enabled: true,
                        distance: -40,
                        format: "{point.percentage:.1f}%",
                        style: {
                            fontSize: "1.2em",
                            textOutline: "none",
                        },
                        filter: {
                            operator: ">",
                            property: "percentage",
                            value: 10,
                        },
                    },
                ],
            },
        },
        series: [
            {
                name: "Median Income ($)",
                data: [
                    { name: "Black", y: 51550 },
                    { name: "White", y: 77378, sliced: true, selected: true },
                    { name: "Hispanic", y: 67018 },
                    { name: "Asian", y: 92788 },
                ],
            },
        ],
    };
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div class="chart">
                <Chart {options} highcharts={Highcharts} />
            </div>

            <div>
               <p>
    This pie chart illustrates the distribution of median income by race in Miami-Dade County, 2023. 
    It visually highlights the economic disparities faced by different racial and ethnic groups.
</p>
<p>
    Understanding these imbalances is critical when addressing racial wealth gaps and designing equitable policy interventions.
</p>
<p>
    Hover over each slice to see how each group compares to the county’s overall median income of $78,538.
</p>

            </div>
        {/snippet}

        {#snippet scrolly()}
           <ArticleText>
    According to the <a href="https://www.census.gov/quickfacts/fact/table/US/SEX255223" target="_blank">U.S. Census Bureau (2019–2023)</a>, 
    the median household income in Miami-Dade County was <strong>$78,538</strong> in 2023 dollars.
</ArticleText>

<ArticleText>
    While this overall figure may seem stable, it masks significant racial disparities in income levels. 
    Not all communities benefit equally from economic growth.
</ArticleText>

<ArticleText>
    White and Asian households report higher median incomes, while Black or African American and Hispanic or Latino households face larger income constraints.
</ArticleText>

<ArticleText>
    These disparities are rooted in longstanding issues of access, whether in employment, education, or intergenerational wealth-building opportunities.
</ArticleText>

<ArticleText>
    <a href="https://blackwealthdata.org/explore/employment#EMP-08" target="_blank">Data from the Black Wealth Data Center</a> confirms these inequities. 
    Economic gaps often translate into lower homeownership rates and limited financial security for marginalized groups.
</ArticleText>

<ArticleText>
    <a href="https://github.com/armirchandani/MedianIncome" target="_blank">Supplementary analysis on GitHub</a> supports this trend, showing a consistent pattern of income inequality across racial groups in Miami-Dade County.
</ArticleText>

<ArticleText>
    <strong>Income is more than a statistic, it determines access to opportunity and shapes the lived reality of communities across Miami-Dade.</strong>
</ArticleText>

        {/snippet}
    </Scroller>
</div>

<style>
    .chart {
        width: 90%;
        margin: 0px auto;
    } </style>