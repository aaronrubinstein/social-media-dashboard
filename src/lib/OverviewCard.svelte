<script>
    export let metric;
    export let socialIcon;
    export let metricCount;
    export let metricPercentChange;
    export let platform;
</script>

<div class="card">
    <div class="top-row">
        <h3>{metric}</h3>
        <img src="{socialIcon}" alt="{platform}">
    </div>
    <div class="bottom-row">
        <p>{metricCount}</p>
        <div class="metric-change">
            {#if metricPercentChange > 0}
                <img src="images/icon-up.svg" alt="up icon">
            {:else if metricPercentChange < 0}
                <img src="images/icon-down.svg" alt="down icon">
            {/if}
            <span class="metric-pct-change {metricPercentChange > 0 ? 'increase' : 'decrease'}">{Math.abs(metricPercentChange)}%</span>
        </div>
    </div>
</div>

<style>

    .card {
        display: flex;
        flex-direction: column;
        gap: 21px;
        background: var(--card-bg);
        height: 125px;
        width: 255px;
        border-radius: 5px;
        padding: 26px 31px 19px 24px;
    }

    .card:hover {
        background: var(--card-bg-hover);
    }

    .top-row {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
    }

    .bottom-row {
        display: flex;
        justify-content: space-between;
        align-items: baseline;
    }

    p {
        font-size: 2rem;
        font-weight: 700;
        line-height: 2.421rem;
        color: var(--text-primary);
    }

    .metric-change {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 4px;
    }

    .metric-pct-change {
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