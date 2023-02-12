<script>
    import SummaryCard from "./lib/SummaryCard.svelte";
    import ThemeToggle from "./lib/ThemeToggle.svelte";
    import OverviewCard from "./lib/OverviewCard.svelte";

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
                platform: 'facebook',
                metricCount: '87',
                metricPercentChange: 3
            },
            {
                metric: 'Likes',
                socialIcon: 'images/icon-facebook.svg',
                platform: 'facebook',
                metricCount: '52',
                metricPercentChange: -2
            },
            {
                metric: 'Likes',
                socialIcon: 'images/icon-instagram.svg',
                platform: 'instagram',
                metricCount: '5462',
                metricPercentChange: 2257
            },
            {
                metric: 'Profile Views',
                socialIcon: 'images/icon-instagram.svg',
                platform: 'instagram',
                metricCount: '52k',
                metricPercentChange: 1375
            },
            {
                metric: 'Retweets',
                socialIcon: 'images/icon-twitter.svg',
                platform: 'twitter',
                metricCount: '117',
                metricPercentChange: 303
            },
            {
                metric: 'Likes',
                socialIcon: 'images/icon-twitter.svg',
                platform: 'twitter',
                metricCount: '507',
                metricPercentChange: 553
            },
            {
                metric: 'Likes',
                socialIcon: 'images/icon-youtube.svg',
                platform: 'youtube',
                metricCount: '107',
                metricPercentChange: -19
            },
            {
                metric: 'Total Views',
                socialIcon: 'images/icon-youtube.svg',
                platform: 'youtube',
                metricCount: '1407',
                metricPercentChange: -12
            },
        ]
    };    

</script>

<div class="top-background"></div>

<header>
    <div class="header-left">
        <h1>Social Media Dashboard</h1>
        <h3>Total Followers: {data.totalFollowers.toLocaleString("en-US")}</h3>
    </div>
    <div class="header-right">
        <ThemeToggle/>
    </div>
</header>

<main>
    <div class="summary-container">
        {#each data.summaryStats as stat}
            <SummaryCard {...stat}/>
        {/each}
    </div>
    <h2>Overview - Today</h2>
    <div class="overview-container">
        {#each data.overviewStats as stat}
            <OverviewCard {...stat}/>
        {/each}
    </div>
</main>

<style>

    header {
        max-width: 1110px;
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 2.875rem;
    }

    h1 {
        margin-bottom: 0.188rem;
    }

    h2 {
        margin-bottom: 1.5rem;
    }

    .summary-container {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 1.875rem;
        margin-bottom: 2.875rem;
        row-gap: 1.5rem;
    }

    .overview-container {
        display: grid;
        grid-template: repeat(4, 1fr) / repeat(4, 1fr);
        column-gap: 1.875rem;
        row-gap: 1.5rem;
    }

    .top-background {
        position:absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 244px;
        border-radius: 0 0 20px 20px;
        background: var(--top-bg-pattern);
        z-index: -1;
    }

</style>
