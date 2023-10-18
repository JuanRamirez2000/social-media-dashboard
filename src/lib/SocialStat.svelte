<script lang="ts">
	import '../themes.css';

	export let socialIcon: string;
	export let socialPlatform: string;
	export let socialFollowing: string;
	export let socialFollowingDescription: string;
	export let socialFollowingPercentChange: string;
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
		<ul>
			<li><p>{socialFollowingDescription}</p></li>
			<li><img src={socialIcon} alt={socialPlatform} /></li>
			<li><h2>{socialFollowing}</h2></li>
			<li
				class:status-positive={positiveSocialChange}
				class:status-negative={!positiveSocialChange}
			>
				{#if positiveSocialChange}
					<img src="/assets/images/icon-up.svg" alt="Change arrow direction" />
				{:else}
					<img src="/assets/images/icon-down.svg" alt="Change arrow direction" />
				{/if}
				<p>{socialFollowingPercentChange}%</p>
			</li>
		</ul>
	</section>
</div>

<style>
	section {
		border-radius: 0.5rem;
		width: 350px;
		height: 150px;
		background-color: var(--card-background);
		display: flex;
		flex-direction: column;
		align-items: center;
		cursor: pointer;
	}

	section:hover {
		background-color: var(--card-background-hover);
	}
	ul {
		width: 80%;
		height: 100%;
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: 1fr 1fr;
	}

	/* Left side */
	ul > li:nth-child(odd) {
		justify-self: start;
		align-self: center;
	}

	/* Right side */
	ul > li:nth-child(even) {
		justify-self: end;
		align-self: center;
	}

	/* Top left */
	ul > li:first-child {
		font-weight: 700;
		color: var(--text-secondary);
	}

	ul > li:nth-child(2) > img {
		height: 1.5rem;
		width: 1.5rem;
	}

	/* Bottom left */
	ul > li:nth-last-child(2) {
		font-size: 3rem;
		font-weight: 700;
		color: var(--text-primary);
	}

	/* Bottom right */
	ul > li:last-child {
		display: flex;
		flex-direction: row;
		align-items: center;
		gap: 2px;
		color: var(--status-color);
		font-weight: 700;
	}

	ul > li:last-child > img {
		height: 0.5rem;
		width: 0.75rem;
	}
</style>
