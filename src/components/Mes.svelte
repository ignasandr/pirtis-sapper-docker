<script>
import Sponsors from "./Sponsors.svelte";

</script>
<div id="mes">
	<div class="video">
		<!-- <iframe src="https://player.vimeo.com/video/336812660?title=0&byline=0&portrait=0" title="nanook" align="left" width="100%" height="100%" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe> -->
		<img src="./img/debesys.jpg" alt="debesys">
		<div class="description">
			<p>Projekto autorės Karolina Latvytė-Bibiano ir Judita Ragauskaitė.
				Projektas sukurtas kartu su „Kauno bienale” ir „Magic Carpets”.
				Nuoširdžiai dėkojame už pagalbą ir bendradarbiavimą:
				„Kaunas 2022”, "Kaunas 3022"; „Ten kur gera”: Giedriui Bučui, Astai Bučienei;
				Ilonai Latvei ir visiems pirties bičiuliams. Projekto rėmėjas: Lietuvos Kultūros taryba.
			</p>
		</div>
	</div>
	<Sponsors/>
</div>

<style>
	#mes {
		position: relative;
		height: 100vh;
		text-align: center;
        background-image: url(../img/backgrounds/bottom.jpg);
        background-position: center;
        background-repeat: no-repeat;
		background-size: cover;
	}
	
	.video {
		display: inline-block;
		margin-left: 20vw;
		margin-top: 20vh;
		width: 54vw;
		height: 28vw;
	}

	.description {
		display: inline-block;
		/* margin-top: 30px;	 */
		color: #fff;
		text-align: justify;
		font-size: 1vw;
	}

	.video img {
		width: 40vw;
	}

@media (max-width: 576px) {
	#mes {
		display: flex;
        justify-content: center;
        align-items: top;
	}
    .video {
        margin: 12vh;
        width: 80vw;
        font-size: 3vw;
	}

    .description {
        margin: 0;
        font-size: 3vw;
	}

	.video img {
		width: 100%;
	}
}
</style>