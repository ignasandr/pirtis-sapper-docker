<script>
    import OneTrack from './OneTrack.svelte';

    let tracks = [
        {id: 1, imgPath: "./img/phones/ausine1.png", audioPath: "./mp3/1.mp3", height: "12", label: "Pirmas garas"},
        {id: 2, imgPath: "./img/phones/ausine2.png", audioPath: "./mp3/2.mp3", height: "23", label: "Vandens milimas"},
        {id: 3, imgPath: "./img/phones/ausine3.png", audioPath: "./mp3/3.mp3", height: "7", label: "Kvėpavimas druska"},
        {id: 4, imgPath: "./img/phones/ausine4.png", audioPath: "./mp3/4.mp3", height: "19", label: "Trynimas"},
        {id: 5, imgPath: "./img/phones/ausine5.png", audioPath: "./mp3/5.mp3", height: "2", label: "Vanojimas"},
        {id: 6, imgPath: "./img/phones/ausine6.png", audioPath: "./mp3/6.mp3", height: "20", label: "Pabaiga"},
    ]

    let current = 0;

    function handleClick(id) {
        id === current ? current = 0 : current = id;
    }
</script>

<div class="tracks">
    {#each tracks as track}
        <OneTrack {...track} active={track.id === current} on:click={() => handleClick(track.id)}/>
    {/each}
</div>

<style>
    .tracks {
        display: grid;
        margin: 0;
        position: relative;
        height: 92vh;
        width: 65vw;
        top: 0;
        left: 30vw;
        grid-template-columns: repeat(6, 1fr);
        gap: 3vw;
    }

@media (max-width: 576px) {
    .tracks {
        top: 10vh;
        grid-template-columns: 1fr 1fr;
        height: 70vh;
        left: 0;
        margin: 0 auto;
        gap: 17vh;
    }
}

@media (max-width: 415px) {
    .tracks {
        gap: 10vh;
    }
}
	

</style>
