<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import clouds from '$lib/assets/clouds.svg';
	import bluesky from '$lib/assets/bluesky.svg';
	import mastodon from '$lib/assets/mastodon.svg';
	import github from '$lib/assets/github.svg';
	import '$lib/assets/style.css';
	import Brand from '$lib/assets/components/Brand.svelte'

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>shroud.social | A privacy-first, decentralized home for your community</title>
	<meta name="description" content="shroud.social, the next generation of private, open-source and decentralized group communication." />
</svelte:head>

<main>
	<header class="hstack">
		<a class="logo" href="/"><Brand variant="mini" style="--brand-size: 48px;"/></a>
		<div class="social-links hstack">
			<a class="social-link" href="https://bsky.app/profile/shroud.social"><img src={bluesky} alt="BlueSky"></a>
			<a class="social-link" href="https://mastodon.social/@shroudsocial"><img src={mastodon} alt="Mastodon"></a>
			<a class="social-link" href="https://github.com/shroud-org"><img src={github} alt="GitHub"></a>
		</div>
		<nav class="hstack">
			<ul>
				<li class="nav-element">
					<a href="#who">Who</a>
				</li>
				<li class="nav-element">
					<a href="#what">What</a>
				</li>
				<li class="nav-element">
					<a href="#where">Where</a>
				</li>
				<li class="nav-element">
					<a href="#when">When</a>
				</li>
				<li class="nav-element">
					<a href="#why">Why</a>
				</li>
			</ul>
		</nav>
	</header>
	<main class="content vstack">
		{@render children()}
	</main>
	<footer class="vstack">
		<div class="info hstack">
			<div class="contacts">
				<h2>Contacts us:</h2>
				<p>support@shroud.social</p>
				<p>support@shroud.org.uk</p>
			</div>
			<div class="company">
				<h2>About:</h2>
				<p>Shroud Labs</p>
			</div>
		</div>
		<div class="brand">
			<Brand style="--brand-size: auto; --brand-width: 100%;" />
			<img src={clouds} alt="clouds" />
		</div>
	</footer>
</main>

<style>
	.vstack {
		display: flex;
		flex-direction: column;
	}

	.hstack {
		display: flex;
		flex-direction: row;
	}

	main {
		background: #14002D;
		background: linear-gradient(190deg, rgba(20, 0, 45, 1) 21%, rgba(24, 99, 165, 1) 100%);
		color: #fff;
	}

	header {
		position: fixed;
		z-index: 100;
		top: 0;
		padding: 32px;
		align-items: center;
		gap: 32px;
		width: 100vw;
		box-sizing: border-box;
	}

	nav {
		display: flex;
		margin-left: auto;
		gap: 20px;
	}

	.social-links {
		gap: 24px;
		align-items: center;
	}

	.social-link img {
		width: 32px;
		opacity: 0.8;
	}

	.social-link:hover {
		opacity: 0.6;
	}

	a {
		text-decoration: none;
		color: #ffffff;
	}

	a:visited {
		color: #fff;
	}

	ul {
		list-style: none;
		padding: 0;
		margin: 0;
		display: flex;
		flex-direction: row;
		gap: 20px;
	}

	li.nav-element {
		font-weight: bold;
		font-size: 18px;
	}

	li.nav-element:hover {
		opacity: 0.8;
	}

	li.nav-element:active {
		opacity: 0.6;
	}

	.content {
		width: 100%;
	}

	footer {
		position: relative;
		padding: 20px 0 1% 0;
		gap: 20px;
	}

	.info {
		padding: 64px;
		display: flex;
		gap: 32px;
	}

	.brand {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 100%;
		padding: 0 2% 0 2%;
		box-sizing: border-box;
		opacity: 87%;
	}

	.brand img {
		position: absolute;
		bottom: 0;
		left: 0;
		width: 100vw;
		opacity: 20%;
		z-index: -1;
	}
</style>