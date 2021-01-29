<script>
</script>

<div id="klausyti">
    <div class="description">
            <p>Šis projektas skirtas pažinti bei garso pagalba nusikelti į lietuvišką pirtį,
            todėl rekomenduojama naudoti ausines, patogiai įsitaisyti ir mėgautis pirties garu. Linkime sušilti:</p>
        <div class="links">
            <a href="Audio">Instaliacija</a>
            <span> | </span>
            <span class="podcast">Podcastas</span>
        </div>
    </div>
</div>

<style>
    #klausyti {
        height: 100vh;
        background-image: url(../img/backgrounds/middle2.jpg);
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }

    .description {
        text-align: justify;
        padding-left: 32vw;
		padding-top: 35vh;
		width: 54vw;
		color: #fff;
    }

	a {
		text-decoration: none;
    }
    .links {
        margin-top: 3vw;
        text-align: center;
        font-size: 1.8vw;
    }
    .podcast {
        color: grey;
    }

@media (max-width: 576px) {
    #klausyti {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    
    .description {
        padding: 0;
        width: 80vw;
        font-size: 3vw;
    }

    .links {
        font-size: 5vw;
    }

}
</style>