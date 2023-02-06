<script>
    import SummaryCard from "./lib/SummaryCard.svelte";
    // import OverviewCard from "./lib/OverviewCard.svelte";

    const data = {
        totalFollowers: 23004,
        summaryStats: [
            {
                socialIcon: 'images/icon-facebook.svg',
                platform: 'facebook',
                username: '@nathanf',
                metric: 'followers',
                metricCount: '1987',
                metricCountChange: 12
            },
            {
                socialIcon: 'images/icon-twitter.svg',
                platform: 'twitter',
                username: '@nathanf',
                metric: 'followers',
                metricCount: '1044',
                metricCountChange: 99
            },
            {
                socialIcon: 'images/icon-instagram.svg',
                platform: 'instagram',
                username: '@realnathanf',
                metric: 'followers',
                metricCount: '11k',
                metricCountChange: 1099
            },
            {
                socialIcon: 'images/icon-youtube.svg',
                platform: 'youtube',
                username: 'Nathan F.',
                metric: 'subscribers',
                metricCount: '8239',
                metricCountChange: -144
            }
        ],
        overviewStats: [
            {
                metric: 'Page Views',
                socialIcon: 'images/icon-facebook.svg',
                metricCount: '87',
                metricPercentChange: 3
            },
            {
                metric: 'Likes',
                socialIcon: 'images/icon-facebook.svg',
                metricCount: '52',
                metricPercentChange: -2
            },
            {
                metric: 'Likes',
                socialIcon: 'images/instagram.svg',
                metricCount: '5462',
                metricPercentChange: 2257
            },
            {
                metric: 'Profile Views',
                socialIcon: 'images/instagram.svg',
                metricCount: '52k',
                metricPercentChange: 1375
            },
            {
                metric: 'Retweets',
                socialIcon: 'images/twitter.svg',
                metricCount: '117',
                metricPercentChange: 303
            },
            {
                metric: 'Likes',
                socialIcon: 'images/twitter.svg',
                metricCount: '507',
                metricPercentChange: 553
            },
            {
                metric: 'Likes',
                socialIcon: 'images/youtube.svg',
                metricCount: '107',
                metricPercentChange: -19
            },
            {
                metric: 'Total Views',
                socialIcon: 'images/youtube.svg',
                metricCount: '1407',
                metricPercentChange: -12
            },
        ]
    };    

</script>

<header>
    <div class="header-left">
        <h1>Social Media Dashboard</h1>
        <h3>Total Followers: {data.totalFollowers.toLocaleString("en-US")}</h3>
    </div>
    <div class="header-right">
        <label for="theme-toggle">Dark Mode</label>
        <input type="checkbox" name="theme-toggle" id="theme-toggle">
    </div>
</header>

<main>
    <div class="summary-container">
        {#each data.summaryStats as stat}
            <SummaryCard {...stat}/>
        {/each}
    </div>
    <h2>Overview - Today</h2>
    <!-- <div class="overview-container">
        {#each data.overviewStats as stat}
            <OverviewCard {...stat}/>
        {/each}
    </div> -->
</main>

<style>

    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 2.875rem;
    }

    .summary-container {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 1.875rem;
        margin-bottom: 2.875rem;
    }

</style>
