<script>
	import BasicCard from "../components/BasicCard.svelte";
	import PageLayout from '../components/PageLayout.svelte';
</script>

<svelte:head>
	<title>Profile</title>
</svelte:head>

<style>
	.horizontal-flex {
		display: flex;
		justify-content:start;
		flex-wrap: wrap;
	}

	.horizontal-flex a {
		margin-right: 1rem;
		color: var(--compliment-2);
	}

	.horizontal-flex a:hover {
		color: var(--hue-3);
	}

</style>


<PageLayout>
	<BasicCard>
		<h2>Amar Singh Gill - Web Developer</h2>
		<p class="horizontal-flex">
			<a title="Send me an email" rel=external href="mailto:amar.s.gill@outlook.com"
			alt="email"><i class="fas fa-envelope-square fa-3x"></i></a>
			<a title="Github profile" href="https://github.com/Amar-Gill" alt="Github" target="_blank"><i class="fab fa-github-square fa-3x"></i></a>
			<a title="LinkedIn profile" href="https://www.linkedin.com/in/amar-s-gill-65860662/" alt="LinkedIn"
			target="_blank"><i class="fab fa-linkedin fa-3x"></i></a>
			<a title="View resume" href="/resume.pdf" target="_blank" alt="resume"><i class="fas fa-file-pdf fa-3x"></i></a>
		</p>
	</BasicCard>

	<BasicCard>
		<h2>Summary</h2>
		<p>Web and Mobile Applications Development</p>
		<p>Current Stack:</p>
		<ul>
			<li><strong>Javascript</strong> Svelte, Sapper</li>
			<li><strong>Google Cloud Platform</strong> Maps JS API, Firebase</li>
		</ul>
	</BasicCard>

	<BasicCard>
		<h2>Personal Projects</h2>
		<p>
			<a href="https://learning-quest.now.sh" target="_blank" alt="learning quest">Learning Quest </a>
			<a href="https://github.com/Amar-Gill/learning-quest" target="_blank"
				alt="learning quest source">[source]</a>
		</p>
		<ul>
			<li>Interactive self guided education tool for children</li>
		</ul>

		<p>
			<a href="https://play.google.com/store/apps/details?id=dev.amar.quizdemo&hl=en" target="_blank" alt="leet quiz">Leet Quiz</a>
			<a href="https://github.com/Amar-Gill/flutter-quizapp" target="_blank"
				alt="learning quest source">[source]</a>
		</p>
		<ul>
			<li>Quiz style game about various topics within web and mobile development</li>
			<li>Available for download in Apple App Store and Google Play Store</li>
		</ul>

		<p>
			<a href="https://array-methods.vercel.app" alt="array methods" target="_blank">Array Methods Visualizer</a>
			<a href="https://github.com/Amar-Gill/array-methods" target="_blank">[source]</a>
		</p>
		<ul>
			<li>Visualization of sorting algorithms used on arrays</li>
		</ul>

	</BasicCard>
</PageLayout>