<script context="module" lang="ts">
	export let videos: {id: string, image: string }[] = [
		{ id: "3JZ_D3ELwOQ", image: 'jorge.png' },
		{ id: "ZJ-k1ZvIunk", image: 'smartist.png' },
		{ id: "pjPOeZ0xEv0", image: 'davidroncero.png' },
		{ id: "GIVtbqQdnpU", image: 'javimonjas.png' },
		{ id: "qzL17fQMYwY", image: 'javitoken.png' },
		{ id: "0hfFW52hDrs", image: 'carabantes.png' },
	];


    function getYoutubeThumbnailUrl(imageName: string) {
        return `/talks/${imageName}`;
    }

	function getYoutubeVideoUrl(videoId: string) {
		return `https://www.youtube.com/watch?v=${videoId}`;
	}
</script>

<div class="video-container">
	{#each videos as { id, image }}
		<a
			class="video-thumbnail"
			href={getYoutubeVideoUrl(id)}
			target="_blank"
			rel="noopener noreferrer"
			style="background-image: url({getYoutubeThumbnailUrl(image)});"
		>
		</a>
	{/each}
</div>

<style>
	.video-container {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		gap: 1rem;
	}

	.video-thumbnail {
		position: relative;
		width: 300px;
		height: 300px;
		background-size: cover;
		background-position: center;
		cursor: pointer;
	}
</style>
