<script>
    export let title = "Snowy reviews";
</script>

<div class="title">
    <img src="/img.svg" alt="controller">
    <h1>{title}</h1>
</div>

<style>

    .title {
        display: flex;
    }
    .title img {
        display: inline-block;
        filter: invert(88%) sepia(18%) saturate(886%) hue-rotate(199deg) brightness(100%) contrast(90%);
        width:80px;
        height:80px;

    }
    .title h1 {
        margin-left: 10px;
    }
</style>