<script>
	import BasicCard from "../components/BasicCard.svelte";
	import PageLayout from '../components/PageLayout.svelte';
</script>

<svelte:head>
	<title>Profile</title>
</svelte:head>


	<PageLayout>
		<BasicCard>
			<h2>Amar Singh Gill - Web Developer - Level 93 Zealadin</h2>
			<p><strong>Email</strong> <a rel=external href="mailto:amar.s.gill@outlook.com"
					alt="email">amar.s.gill@outlook.com</a>
			</p>
			<p><strong>Github</strong> <a href="https://github.com/Amar-Gill" alt="Github" target="_blank">Amar-Gill</a>
			</p>
			<p><strong>LinkedIn</strong> <a href="https://www.linkedin.com/in/amar-s-gill-65860662/" alt="LinkedIn"
					target="_blank">Amar Gill</a></p>
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
				<a href="https://learning-quest.now.sh" target="_blank" alt="learning quest">Learning Quest	</a>
				<a href="https://github.com/Amar-Gill/learning-quest" target="_blank" alt="learning quest source">[source]</a>
			</p>
			<ul>
				<li>Interactive self guided education tool for children</li>
			</ul>
		</BasicCard>
	</PageLayout>