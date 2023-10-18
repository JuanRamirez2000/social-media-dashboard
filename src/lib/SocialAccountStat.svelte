<script lang="ts">
	import '../themes.css';

	export let socialIcon: string;
	export let socialPlatform: string;
	export let socialTag: string;
	export let socialFollowing: string;
	export let socialFollowingDescription: string;
	export let socialFollowingDailyChange: string;
	export let positiveSocialChange: boolean;
</script>

<div
	class="border"
	class:socials-facebook={socialPlatform === 'facebook'}
	class:socials-twitter={socialPlatform === 'twitter'}
	class:socials-instagram={socialPlatform === 'instagram'}
	class:socials-youtube={socialPlatform === 'youtube'}
>
	<section>
		<header>
			<img src={socialIcon} alt={socialPlatform} />
			<p>{socialTag}</p>
		</header>
		<main>
			<h2>{socialFollowing}</h2>
			<p>{socialFollowingDescription.toLocaleUpperCase()}</p>
		</main>
		<footer
			class:status-positive={positiveSocialChange}
			class:status-negative={!positiveSocialChange}
		>
			{#if positiveSocialChange}
				<img src="/assets/images/icon-up.svg" alt="Change arrow direction" />
			{:else}
				<img src="/assets/images/icon-down.svg" alt="Change arrow direction" />
			{/if}
			<p>{socialFollowingDailyChange} Today</p>
		</footer>
	</section>
</div>

<style>
	.border {
		height: fit-content;
		width: fit-content;
		padding-top: 5px;
		background: var(--social-color);
		border-radius: 0.5rem;
	}

	section {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		text-align: center;
		width: 350px;
		height: 250px;
		background-color: var(--card-background);
		gap: 2rem;
		cursor: pointer;
	}

	section:hover {
		background-color: var(--card-background-hover);
	}

	header {
		display: flex;
		flex-direction: row;
		align-items: center;
		gap: 0.5rem;
	}
	header > p {
		color: var(--text-secondary);
		font-weight: 700;
	}

	main > h2 {
		font-size: 4rem;
		font-weight: 700;
		color: var(--text-primary);
	}
	main > p {
		letter-spacing: 0.25rem;
		color: var(--text-secondary);
	}

	footer {
		display: flex;
		flex-direction: row;
		align-items: center;
		gap: 0.25rem;
		color: var(--status-color);
		font-weight: 700;
	}

	footer > img {
		height: 0.5rem;
		width: 0.5rem;
	}
</style>
