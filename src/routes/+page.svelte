<script>
	import TwitchPlugin from '../lib/TwitchPlugin.svelte';
	import TalksThumbnails from '../lib/TalksThumbnails.svelte';
	import logo from '$lib/images/divancelogo.png';
	import github from '$lib/images/github.svg';
	import discord from '$lib/images/discord.svg';
	import tiktok from '$lib/images/tiktok.svg';

	const videos = [];
</script>

<svelte:head>
	<title>Twitch</title>
	<meta name="description" content="About this app" />
</svelte:head>

<div class="text-row">
	<div class="column">
	  <TwitchPlugin channel="divance-twitch" />
	</div>
	<div class="column">
	  <h1>Welcome to Divance ! 👋</h1>
	  <div class="social-icons">
		<ul>
		  <li>
			<div class="icon">
			  <a href="https://discord.com/invite/fXP5juJqQa">
				<img src={discord} width="32px" height="32px" alt="Discord" />
			  </a>
			</div>
		  </li>
		  <li>
			<div class="icon">
			  <a href="https://www.tiktok.com/@divance_twitch">
				<img src={tiktok} width="32px" height="32px" alt="tiktok" />
			  </a>
			</div>
		  </li>
		  <li>
			<div class="icon">
			  <a href="https://github.com/divance-cryptos">
				<img src={github} width="32px" height="32px" alt="GitHub" />
			  </a>
			</div>
		  </li>
		</ul>
	  </div>
	</div>
  </div>

<div>
	<h1>Season 1 talks</h1>
	<TalksThumbnails />
</div>

<style>
	.text-row {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: center;
		align-items: flex-start;
		margin: 0 auto;
	}
	.column {
		padding: 1rem;
		width: 500px;
		box-sizing: border-box;
	}

	.social-icons {
		display: flex;
		justify-content: space-between;
	}
	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	li[aria-current='page']::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--color-theme-1);
	}
</style>
