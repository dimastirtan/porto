<script>
    export let cardTitle;
    export let cardDescription;
</script>

<div class="card">
    <h3>{cardTitle}</h3>
    <p>{cardDescription}</p>
    <slot></slot>
</div>

<style>
    .card {
        border: 1px solid #ddd;
        border-radius: 8px;
        padding: 16px;
        margin: 16px 0;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    }

    h3 {
        margin-top: 0;
    }

    p {
        color: #555;
    }
</style>