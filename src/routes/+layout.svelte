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
	<title>shroud.social</title>
</svelte:head>

<main>
	<header>
		<nav>
			<a class="logo" href="/"><Brand variant="mini" style="--brand-size: 48px;"/></a>
			<div class="social-links">
				<a class="social-link" href="https://bsky.app/profile/shroud.social"><img src={bluesky} alt="BlueSky"></a>
				<a class="social-link" href="https://mastodon.social/@shroudsocial"><img src={mastodon} alt="Mastodon"></a>
				<a class="social-link" href="https://github.com/shroud-org"><img src={github} alt="GitHub"></a>
			</div>
		</nav>
	</header>
	<div class="content">
		{@render children()}
	</div>
	<footer>
		<div class="socials"></div>
		<div class="brand">
			<Brand style="--brand-size: auto; --brand-width: 100%;" />
			<img src={clouds} alt="clouds" />
		</div>
	</footer>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		background: #14002D;
		background: linear-gradient(190deg, rgba(20, 0, 45, 1) 21%, rgba(24, 99, 165, 1) 100%);
		color: #fff;
	}

	nav {
		padding: 32px;
		display: flex;
		flex-direction: row;
		align-items: center;
		gap: 20px;
		width: 100%;
	}

	.social-links {
		display: flex;
		gap: 25px;
		padding-left: 15px;
		align-items: center;
	}

	.social-link img {
		width: 32px;
		opacity: 0.8;
	}

	.social-link:hover {
		opacity: 0.6;
	}

	ul {
		list-style: none;
		margin: 0;
		padding: 0;
		display: flex;
		width: 100%;
		height: 50px;
		justify-content: center;
		align-items: center;
		gap: 1rem;
	}

	a {
		text-decoration: none;
	}

	a:visited {
		color: #fff;
	}

	.content {
		flex: 1;
		width: 100vw;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding-bottom: 1%;
	}

	.brand {
		width: 95%;
		opacity: 87%;
	}

	.brand img {
		position: absolute;
		bottom: 0;
		left: 0;
		width: 100vw;
		height: auto;
		opacity: 20%;
		z-index: -1;
	}
</style>