<script>
	import SocialAccountStat from '$lib/SocialAccountStat.svelte';
	import SocialStat from '$lib/SocialStat.svelte';
	import '../themes.css';

	let darkMode = false;
</script>

<div class="mainPage" class:light-theme={!darkMode} class:dark-theme={darkMode}>
	<header>
		<div class="dashboardTitle">
			<h1>Social Media Dashboard</h1>
			<p>Total Followers: 23,004</p>
		</div>
		<hr />
		<div class="darkModeToggleContainer">
			<h2>Dark Mode</h2>
			<input class="toggle" type="checkbox" bind:checked={darkMode} />
		</div>
	</header>
	<main>
		<div class="socialAccountsContainer">
			<SocialAccountStat
				socialIcon="/assets/images/icon-facebook.svg"
				socialPlatform="facebook"
				socialTag="@nathanf"
				socialFollowing="1987"
				socialFollowingDescription="followers"
				socialFollowingDailyChange="12"
				positiveSocialChange={true}
			/>
			<SocialAccountStat
				socialIcon="/assets/images/icon-twitter.svg"
				socialPlatform="twitter"
				socialTag="@nathanf"
				socialFollowing="1044"
				socialFollowingDescription="followers"
				socialFollowingDailyChange="99"
				positiveSocialChange={true}
			/>
			<SocialAccountStat
				socialIcon="/assets/images/icon-instagram.svg"
				socialPlatform="instagram"
				socialTag="@realnathanf"
				socialFollowing="11k"
				socialFollowingDescription="followers"
				socialFollowingDailyChange="1099"
				positiveSocialChange={true}
			/>
			<SocialAccountStat
				socialIcon="/assets/images/icon-youtube.svg"
				socialPlatform="youtube"
				socialTag="Nathan F."
				socialFollowing="8239"
				socialFollowingDescription="subscribers"
				socialFollowingDailyChange="144"
				positiveSocialChange={false}
			/>
		</div>
		<h1>Overview - Today</h1>
		<div class="socialStatContainer">
			<SocialStat
				socialIcon="/assets/images/icon-facebook.svg"
				socialPlatform="facebook"
				socialFollowing="87"
				socialFollowingDescription="Page Views"
				socialFollowingPercentChange="3"
				positiveSocialChange={true}
			/>
			<SocialStat
				socialIcon="/assets/images/icon-facebook.svg"
				socialPlatform="facebook"
				socialFollowing="52"
				socialFollowingDescription="Likes"
				socialFollowingPercentChange="2"
				positiveSocialChange={false}
			/>
			<SocialStat
				socialIcon="/assets/images/icon-instagram.svg"
				socialPlatform="instagram"
				socialFollowing="5462"
				socialFollowingDescription="Likes"
				socialFollowingPercentChange="2257"
				positiveSocialChange={true}
			/>
			<SocialStat
				socialIcon="/assets/images/icon-instagram.svg"
				socialPlatform="instagram"
				socialFollowing="52k"
				socialFollowingDescription="Profile Views"
				socialFollowingPercentChange="1375"
				positiveSocialChange={true}
			/>
			<SocialStat
				socialIcon="/assets/images/icon-twitter.svg"
				socialPlatform="twitter"
				socialFollowing="117"
				socialFollowingDescription="Retweets"
				socialFollowingPercentChange="303"
				positiveSocialChange={true}
			/>
			<SocialStat
				socialIcon="/assets/images/icon-twitter.svg"
				socialPlatform="twitter"
				socialFollowing="507"
				socialFollowingDescription="Likes"
				socialFollowingPercentChange="553"
				positiveSocialChange={true}
			/>
			<SocialStat
				socialIcon="/assets/images/icon-youtube.svg"
				socialPlatform="youtube"
				socialFollowing="107"
				socialFollowingDescription="Likes"
				socialFollowingPercentChange="19"
				positiveSocialChange={false}
			/>
			<SocialStat
				socialIcon="/assets/images/icon-youtube.svg"
				socialPlatform="youtube"
				socialFollowing="1407"
				socialFollowingDescription="Total Views"
				socialFollowingPercentChange="12"
				positiveSocialChange={false}
			/>
		</div>
	</main>
</div>

<style>
	div.mainPage {
		display: flex;
		width: 100%;
		height: 100%;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		background-color: var(--page-background);
	}

	header {
		display: flex;
		flex-direction: column;
		align-items: start;
		padding-top: 3rem;
		padding-bottom: 3rem;
		gap: 1rem;
		width: 350px;
		background-color: var(--top-background-pattern);
	}

	header > div > h1 {
		font-size: 1.5rem;
		font-weight: 700;
		color: var(--text-primary);
	}

	header > div > p {
		color: var(--text-secondary);
		font-weight: 700;
	}

	hr {
		width: 100%;
		margin-top: 1rem;
		margin-bottom: 1rem;
	}

	.darkModeToggleContainer {
		display: flex;
		width: 100%;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
	}

	.darkModeToggleContainer > h2 {
		font-size: 1rem;
		font-weight: 700;
		color: var(--text-secondary);
	}

	input {
		-webkit-appearance: none;
		-moz-appearance: none;
		appearance: none;
		width: 4rem;
		height: 2rem;
		display: inline-block;
		position: relative;
		border-radius: 50px;
		overflow: hidden;
		outline: none;
		border: none;
		cursor: pointer;
		background: var(--toggle-color);
		transition: background-color ease 0.3s;
	}

	input::before {
		content: ' ';
		display: block;
		position: absolute;
		z-index: 10;
		width: 1.5rem;
		height: 1.5rem;
		background: var(--top-background-pattern);
		left: 0.25rem;
		top: 0.25rem;
		border-radius: 50%;
		transition: all cubic-bezier(0.3, 1.5, 0.7, 1) 0.3s;
	}

	input:checked::before {
		left: 2.25rem;
	}

	.socialAccountsContainer {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 10px;
		width: 100%;
	}

	.socialStatContainer {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 20px;
		width: 100%;
		padding-bottom: 4rem;
	}

	main > h1 {
		font-size: 1.5rem;
		font-weight: 700;
		color: var(--text-secondary);
		padding-top: 3rem;
		padding-bottom: 3rem;
	}

	@media screen and (min-width: 480px) {
		div.mainPage {
			width: 100vw;
			height: 100vh;
		}
		hr {
			display: none;
		}

		header,
		main {
			width: 80%;
		}

		header {
			display: flex;
			flex-direction: row;
			justify-content: space-between;
		}

		header > div > h1 {
			font-size: 2rem;
		}

		.dashboardTitle {
			width: 50%;
		}

		.darkModeToggleContainer {
			display: flex;
			flex-direction: row;
			justify-content: end;
		}

		.socialAccountsContainer {
			display: grid;
			grid-template-columns: repeat(4, 1fr);
		}
		.socialStatContainer {
			display: grid;
			grid-template-columns: repeat(4, 1fr);
			grid-template-rows: 1fr 1fr;
		}
	}
</style>
