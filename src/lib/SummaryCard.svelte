<script>
    export let socialIcon;
    export let platform;
    export let username;
    export let metric;
    export let metricCount;
    export let metricCountChange;
</script>

<div class="card {platform}">
    <div class="top-row">
        <img src="{socialIcon}" alt="{platform}">
        <span class="username">{username}</span>
    </div>
    <div class="middle-row">
        <p class="metric-count">{metricCount}</p>
        <p class="metric">{metric}</p>
    </div>
    <div class="bottom-row">
        {#if metricCountChange > 0}
            <img src="images/icon-up.svg" alt="up icon">
        {:else if metricCountChange < 0}
            <img src="images/icon-down.svg" alt="down icon">
        {/if}
        <span class="metric-count-change {metricCountChange > 0 ? 'increase' : 'decrease'}">{Math.abs(metricCountChange)} Today</span>
    </div>
</div>

<style>
    .card {
        display: flex;
        flex-direction: column;
        align-items: center;
        background: var(--card-bg);
        height: 216px;
        width: 100%;
        border-radius: 5px;
    }

    .card:hover {
        background: var(--card-bg-hover);
    }

    .card.facebook {
        border-top: 4px solid var(--facebook);
    }
    .card.twitter {
        border-top: 4px solid var(--twitter);
    }
    .card.instagram {
        /* https://codyhouse.co/nuggets/css-gradient-borders */
        background: linear-gradient(var(--card-bg), var(--card-bg)) padding-box,
            linear-gradient(225deg, #DF4896 0%, #EE877E 50.91%, #FDC366 100%) border-box;
        border-top: 4px solid transparent;
    }
    .card.instagram:hover{
        background: linear-gradient(var(--card-bg-hover), var(--card-bg-hover)) padding-box,
            linear-gradient(225deg, #DF4896 0%, #EE877E 50.91%, #FDC366 100%) border-box;
    }
    .card.youtube {
        border-top: 4px solid var(--youtube);
    }

    .top-row {
        display: flex;
        align-items: center;
        gap: 8px;
        margin-top: 32px;
    }

    .username {
        font-size: 0.75rem;
        font-weight: 700;
        line-height: 0.908rem;
        color: var(--text-secondary);
    }

    .middle-row {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 9px;
        margin-top: 28px;
        margin-bottom: 25px;
    }

    .metric-count {
        font-size: 3.5rem;
        font-weight: 700;
        line-height: 3rem;
        color: var(--text-primary);
    }

    .metric {
        font-size: 0.75rem;
        font-weight: 400;
        line-height: 0.908rem;
        color: var(--text-secondary);
        text-transform: uppercase;
        letter-spacing: 5px;
    }

    .bottom-row {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 4px;
    }

    .metric-count-change {
        font-size: 0.75rem;
        font-weight: 700;
        line-height: 0.908rem;
    }

    .increase {
        color: var(--lime-green);
    }

    .decrease {
        color: var(--bright-red);
    }

</style>