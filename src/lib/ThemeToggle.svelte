<script>
    let lightTheme = false;
    $: if (lightTheme) {
        document.body.classList.add('light');
    } else {
        document.body.classList.remove('light');
    }
</script>

<div class="container">
    <div class="text">Dark Mode</div>
    <label class="switch">
        <input type="checkbox" bind:checked={lightTheme}>
        <span class="slider"></span>
    </label>
</div>

<style>

    .container {
        display: flex;
        align-items: center;
    }

    /* https://codyhouse.co/nuggets/styling-siblings-on-hover */
    .container:hover .text:not(:hover) {
        color: var(--toggle-text-hover);
    }

    .text {
        font-size: 0.875rem;
        font-weight: 700;
        line-height: 1.5rem;
        padding-right: 13px;
        color: var(--text-secondary);
    }
    
    .switch {
        position: relative;
        display: inline-block;
        width: 48px;
        height: 24px;
    }

    .switch input { 
        opacity: 0;
        width: 0;
        height: 0;
    }

    .slider {
        position: absolute;
        cursor: pointer;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        border-radius: 24px;
        background: var(--toggle-bg);
        /* transition: .4s; */
    }

    .slider:before {
        position: absolute;
        content: "";
        height: 18px;
        width: 18px;
        border-radius: 50%;
        left: 4px;
        bottom: 3px;
        background-color: var(--toggle-slider);
        transition: .4s;
    }

    input:checked + .slider {
        background: var(--toggle-bg);
    }

    /* input:checked + .slider:hover {
        background: var(--toggle-bg);
    } */

    /* input:focus + .slider {
        box-shadow: 0 0 1px hsl(230, 22%, 74%);
    } */

    input:checked + .slider:before {
        transform: translateX(22px);
        background-color: var(--toggle-slider);
    }

    .switch:hover .slider {
        background: var(--toggle-bg-hover);
    }

</style>