<script>
	let isOpen = false;
	export let segment;
	function toggleNav() {
		isOpen = !isOpen;
	}
</script>

<style>
	@media(min-width: 769px) {
		nav {
			border-bottom: solid gray 1px;
		}
	}
</style>

<nav class="navbar" aria-label="main navigation">
	<div class="navbar-brand">
		<a rel="prefetch" href="/" class="navbar-item">
			<img src="logo.jpg" alt="virus" />
		</a>
		<span class="navbar-burger" on:click={toggleNav} class:is-active={isOpen} aria-label="menu" aira-expanded="false" >
			<span aria-hidden="true"></span>
			<span aria-hidden="true"></span>
			<span aria-hidden="true"></span>
		</span>
	</div>
	<div class="navbar-menu" class:is-active={isOpen}>
		<div class="navbar-start">
			<a rel="prefetch" href="/" class="navbar-item" class:is-active={segment === undefined}>Home</a>
			<a rel="prefetch" href="/about" class="navbar-item"  class:is-active={segment === 'about'}>About</a>
		</div>
	</div>
</nav>
