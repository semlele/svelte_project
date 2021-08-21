<script>
    export let label = "";
    export let value = 0;
</script>

<div class="container">
    <div class="label">{label}</div>
    <div class="bar" style="--value: {value}px"></div>
</div>

<style>
    .container {
        display: flex;
        align-items: center;
        height: 1.5em;
        padding: 0.2em 0;
    }

    .label {
        margin-right: 0.5em;
        width: 4em;
        text-align: right;
    }

    .bar {
        background-color: white;
        height: 100%;
        width: var(--value, 0);
    }
</style>