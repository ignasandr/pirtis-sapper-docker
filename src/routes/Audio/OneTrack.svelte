<script context="module">
    let current;
</script>

<script>
    export let id, imgPath, audioPath, active, height, label;

    let audio;
    let paused = true;

    function stopOthers() {
        if (current && current !== audio) current.pause();
        current = audio;
    }

    function startPlaying() {
        if (paused) {
            audio.currentTime = 0;
            audio.play();
        }
        else {
            audio.pause();
        }
    }

</script>

<div id="track{id}" class="{active ? "OneTrack active" : "OneTrack"}" on:click style="--height: {height}vw">
    <img src={imgPath} alt="phones" on:click={startPlaying}> 
    <div class="label">{label}</div>
    <audio
        bind:this={audio}
        bind:paused
        on:play={stopOthers}
        loop
        src={audioPath}
        >
        <track kind="captions">
    </audio>
</div>

<style>
    .OneTrack {
        max-height: 38vh;
        position: relative;
        opacity: 40%;
        transition: opacity 0.5s ease-in-out;
        z-index: inherit;
        top: var(--height);
        user-select: none;
    }

    .OneTrack:hover {
        opacity: 100%;
    }

    img {
        position: absolute;
        left: 0;
        bottom: 5vh;
        max-width: 100%;
        cursor: pointer;
    }

    .label {
        position: absolute;
        font-size: 1.3vw;
        right: 1vw;
        top: 33vh;
        text-align: right;
    }

    .active {
        opacity: 100%;
    }

@media (max-width: 576px) {
    .label {
        /* position: relative; */
        top: 6vh;
        font-size: 3vw;
    }
}

@media (max-width: 415px) {
    .label {
        top: 12vh;
    }
}

</style>
