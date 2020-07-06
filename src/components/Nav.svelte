<script>
	export let segment;
</script>

<style>
	nav {
		border-bottom: 1px solid var(--hue-2);
		font-weight: 300;
		padding: 0 1em;
		background-color: var(--hue-1);
	}

	ul {
		margin: 0;
		padding: 0;
	}

	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	li {
		display: block;
		float: left;
	}

	a {
		text-decoration: none;
		padding: 1rem 0.5rem;
		display: block;
		filter: grayscale(100%) opacity(0.7);
		color: var(--hue-3);
	}

	a:active {
		color: var(--compliment-2);
		filter: grayscale(0%) opacity(1);
	}

	/* styling of active link for present page */
	[aria-current] {
		position: relative;
		display: inline-block;
		font-weight: 600;
		filter: grayscale(0%) opacity(1);
	}

	/* styling of active link underline */
	[aria-current]::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		background-color: var(--hue-3);
		display: block;
		bottom: -1px;
	}
</style>

<nav>
	<ul>
		<li><a aria-current='{segment === undefined ? "page" : undefined}' href='.'>Resume</a></li>
		<li><a aria-current='{segment === "privacy_policy" ? "page" : undefined}' href='privacy_policy'>Privacy
				Policy</a></li>
		<li><a aria-current='{segment === "projects_map" ? "page" : undefined}' href='projects_map'>Projects Map</a>
		</li>

		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
		<!-- <li><a rel=prefetch aria-current='{segment === "blog" ? "page" : undefined}' href='blog'>blog</a></li> -->
	</ul>
</nav>