<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import clouds from '$lib/assets/clouds.svg';
	import bluesky from '$lib/assets/bluesky.svg';
	import mastodon from '$lib/assets/mastodon.svg';
	import github from '$lib/assets/github.svg';
	import { Menu } from '@lucide/svelte';
	import { X } from '@lucide/svelte';
	import '$lib/assets/style.css';
	import Brand from '$lib/assets/components/Brand.svelte'

	let { children } = $props();

	let scrollY = $state(0);
	let innerHeight = $state(0);
	let innerWidth = $state(0);

	let isScrolled = $derived(scrollY > innerHeight - 100);

	let navOpened = $state(false);
	function toggleNav() {
		navOpened = !navOpened;
	}

	let showNavBackground = $derived(isScrolled && innerWidth > 700);
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>shroud.social | A privacy-first, decentralized home for your community</title>
	<meta name="description" content="shroud.social, the next generation of private, open-source and decentralized group communication." />
</svelte:head>

<svelte:window bind:scrollY={scrollY} bind:innerHeight={innerHeight} bind:innerWidth={innerWidth} />

<div class="page">
	<header>
		<div class="logo header-component" class:scrolled={isScrolled}>
			<a href="/"><Brand variant="mini" style="--brand-size: 48px;"/></a>
		</div>
		<div class="social-links header-component" class:scrolled={isScrolled}>
			<a class="social-link" href="https://bsky.app/profile/shroud.social"><img src={bluesky} alt="BlueSky"></a>
			<a class="social-link" href="https://mastodon.social/@shroudsocial"><img src={mastodon} alt="Mastodon"></a>
			<a class="social-link" href="https://github.com/shroud-org"><img src={github} alt="GitHub"></a>
		</div>
		<div class="navigation header-component" class:scrolled={showNavBackground}>
			<nav class:open={navOpened}>
				<ul>
					<li class="nav-element">
						<a href="/#who" onclick={toggleNav}>Who</a>
					</li>
					<li class="nav-element">
						<a href="/#what" onclick={toggleNav}>What</a>
					</li>
					<li class="nav-element">
						<a href="/#where" onclick={toggleNav}>Where</a>
					</li>
					<li class="nav-element">
						<a href="/#when" onclick={toggleNav}>When</a>
					</li>
					<li class="nav-element">
						<a href="/#why" onclick={toggleNav}>Why</a>
					</li>
				</ul>
			</nav>
			<button id="nav-menu" onclick={toggleNav}>
				{#if navOpened}
					<X />
				{:else}
					<Menu />
				{/if}
			</button>
		</div>
	</header>
	<main>
		{@render children()}
	</main>
	<footer>
		<div class="info">
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
</div>

<style lang="scss">
	$small-screen: 700px;
	$medium-screen: 900px;
	$large-screen: 1200px;

	.page {
		background: #14002D;
		background: linear-gradient(190deg, rgba(20, 0, 45, 1) 21%, rgba(24, 99, 165, 1) 100%);
		color: #fff;
	}

	header {
		display: flex;
		flex-direction: row;
		position: fixed;
		z-index: 100;
		top: 0;
		padding: 16px;
		align-items: center;
		gap: 12px;
		width: 100vw;
		box-sizing: border-box;

		.header-component {
			padding: 16px;
			border: 1px solid rgb(255 255 255 / 0);
			border-radius: 50px;
			transition: background 0.3s ease, border 0.3s ease;
		}

		.scrolled {
			background: rgb(0 0 0 / 0.34);
			backdrop-filter: blur(10px);
			border: 1px solid rgb(255 255 255 / 0.2);

			a {
				&:hover {
					opacity: 1;
					background: rgb(0 0 0 / 0.4);
					backdrop-filter: blur(10px);
				}
			}
		}

		a {
			text-decoration: none;
			color: #ffffff;

			&:hover {
				opacity: 0.8;
			}

			&:visited {
				color: #ffffff;
			}
		}

		.logo {
			display: flex;
			height: 48px;
			width: 48px;
		}

		.social-links {
			display: flex;
			flex-direction: row;
			gap: 0;
			justify-content: center;
			align-items: center;
			padding: 4px;

			.social-link {
				line-height: 0;
				display: inline-flex;
				align-items: center;
				padding: 12px;

				img {
					width: 32px;
					height: 32px;
					object-fit: contain;
					opacity: 0.8;
				}
			}
		}

		.navigation {
			margin-left: auto;

			@media screen and (max-width: $small-screen) {
				nav {
					display: none;
					flex-direction: column;
					position: fixed;
					z-index: -1;
					top: 8px;
					left: 50%;
					transform: translateX(-50%);
					width: 95%;
					background: rgb(0 0 0 / 0.4);
					backdrop-filter: blur(10px);
					border: 1px solid rgb(255 255 255 / 0.4);
					border-radius: 48px;

					transition: display 0.3s ease;

					&.open {
						display: flex;
					}

					ul {
						display: flex;
						flex-direction: column;
						justify-content: center;
						align-items: center;
						margin: 0;
						padding: 96px 0 16px 0;
						list-style: none;
						gap: 48px;

						li.nav-element {
							font-weight: bold;
							font-size: 48px;

							&:hover {
								opacity: 0.8;
							}

							&:active {
								opacity: 0.6;
							}

							a {
								padding: 12px;
							}
						}
					}
				}

				button {
					display: inline-block;
					justify-content: center;
					align-items: center;
					height: 48px;
					width: 48px;
					padding: 4px;
					border: none;
					border-radius: 25px;
					background-color: rgb(255 255 255 / 0.87);
					color: #000000;
					line-height: 0;
				}
			}

			@media screen and (min-width: $small-screen) {
				nav {
					display: flex;
					flex-direction: row;

					ul {
						display: flex;
						flex-direction: row;
						list-style: none;
						padding: 0;
						margin: 0;

						li.nav-element {
							font-weight: bold;
							font-size: 18px;

							&:hover {
								opacity: 0.8;
							}

							&:active {
								opacity: 0.6;
							}

							a {
								padding: 12px;
							}
						}
					}
				}

				button {
					display: none;
				}
			}
		}
	}

	main {
		display: flex;
		flex-direction: column;
		width: 100%;
	}

	footer {
		display: flex;
		flex-direction: column;
		position: relative;
		padding: 20px 0 1% 0;
		gap: 20px;

		.info {
			display: flex;
			flex-direction: row;
			padding: 64px;
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

			img {
				position: absolute;
				bottom: 0;
				left: 0;
				width: 100vw;
				opacity: 20%;
				z-index: -1;
			}
		}
	}
</style>