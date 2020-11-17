<script>
    export let imgPath, alt, time;
</script>

<div class="slideshow-item" style="animation-delay: {time}s">
    <img src={imgPath} alt={alt}>
</div>

<style>
    .slideshow-item {
        width: inherit;
        height: inherit;
        position: absolute;
        opacity: 0;
        animation: cycleImages 41s infinite;
    }

    .slideshow-item img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    @keyframes cycleImages {
        25% {
            opacity: 1;
        }
        40% {
            opacity: 0;
        }
    }

</style>