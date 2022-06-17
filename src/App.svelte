<script>
	export let caption = '👋'
	export const address = '0x66b57885E8E9D84742faBda0cE6E3496055b012d'

	function copyAddress() {
		let timer = null
		navigator.clipboard.writeText(address).then(() => {
			caption = '👌'
			clearTimeout(timer)
			timer = setTimeout(() => {
				caption = '👋'
			}, 3000)
		})
	}
</script>

<main>
	<h1>{caption}</h1>
	<ul>
		<li class="rainbow-text" on:click={copyAddress} title={address}>
			<span class="title">ENS</span>
			<span>binrui.eth</span>
		</li>
		<li class="rainbow-text">
			<a target="blank_" href="https://github.com/guanbinrui">
				<span class="title">Github</span>
				<span>guanbinrui</span>
			</a>
		</li>
		<li class="rainbow-text">
			<a target="blank_" href="https://twitter.com/differui">
				<span class="title">Twitter</span>
				<span>@differui</span>
			</a>
		</li>
		<li class="rainbow-text">
			<a target="blank_" href="mailto:hi@guanbinrui.com">
				<span class="title">Mail</span>
				<span>Hi!</span>
			</a>
		</li>
	</ul>
</main>

<style>
	main {
		user-select: none;
		width: 100%;
		height: 100%;
		text-align: center;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
		margin-top: -1em;
	}

	ul {
		font-family: "Work Sans", sans-serif;
		font-size: 14px;
		font-weight: 700;
		list-style-type: none;
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		padding: 0;
		margin: 1em 0;
	}

	li {
		flex: 1;
		padding: 24px 48px;
	}

	li .title {
		font-size: 18px;
	}

	li span {
		text-align: left;
		display: block;
		white-space: nowrap;
	}

	.rainbow-text {
		/* Create a conic gradient. */
		/* Double percentages to avoid blur (#000 10%, #fff 10%, #fff 20%, ...). */
		background: #CA4246;
		background-color: #CA4246;
		background: conic-gradient(
			#CA4246 16.666%, 
			#E16541 16.666%, 
			#E16541 33.333%, 
			#F18F43 33.333%, 
			#F18F43 50%, 
			#8B9862 50%, 
			#8B9862 66.666%, 
			#476098 66.666%, 
			#476098 83.333%, 
			#A7489B 83.333%);
		
		/* Set thee background size and repeat properties. */
		background-size: 57%;
		background-repeat: repeat;
		
		/* Use the text as a mask for the background. */
		/* This will show the gradient as a text color rather than element bg. */
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent; 
		
		/* Animate the text when loading the element. */
		/* This animates it on page load and when hovering out. */
		animation: rainbow-text-animation-rev 0.5s ease forwards;

		cursor: pointer;
	}
</style>