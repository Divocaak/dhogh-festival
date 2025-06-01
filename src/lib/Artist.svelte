<script>
    export let name;
    export let imgPath;
</script>

<div class="artist" style="background-image: url('/imgs/artists/{imgPath}');">
    <h2>{name}</h2>
</div>

<style>
    .artist{
        background-position: center;
        background-repeat: none;
        background-size: cover;
        flex: 1;
        min-height: 500px;
        position: relative;
    }

    .artist h2{
        text-align: center;
        position: absolute;
        bottom: 0;
        width: 100%;
        color: var(--shadow)
    }
</style>