<script>
    import Slide from "./Slide.svelte";

    let slides = [
        {imgPath: "./img/show/bp1.jpg", alt: "slide1", time: 0},
        {imgPath: "./img/show/bp2.jpg", alt: "slide2", time: 10},
        {imgPath: "./img/show/bp3.jpg", alt: "slide3", time: 20},
        {imgPath: "./img/show/bp4.jpg", alt: "slide4", time: 30},
    ];
</script>

<div id="slideshow">
   {#each slides as slide}
        <Slide {...slide}/>
   {/each}
</div>


<style>
    #slideshow {
        width: 100%;
        height: 100vh;
        position: relative;
        overflow: hidden;
    }
</style>