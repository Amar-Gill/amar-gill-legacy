<script>
	import BasicCard from "../components/BasicCard.svelte";
</script>


<style>
	section {
		max-width: 56em;
		padding-top: 1em;
		padding-left: 10rem;
		padding-right: 10rem;
	}

	@media (max-width: 835px) {
		section {
			padding-left: 1rem;
			padding-right: 1rem;
		}
	}

	a {
		color: var(--hue-2);
	}

	a:visited {
		color: var(--hue-2);
	}
</style>

<svelte:head>
	<title>Profile</title>
</svelte:head>

<section>
	<BasicCard>
		<h2>Amar Singh Gill - Full Stack Developer</h2>
		<p><strong>Email</strong> <a href="mailto:amar.s.gill@outlook.com" alt="email">amar.s.gill@outlook.com</a></p>
		<p><strong>Github</strong> <a href="https://github.com/Amar-Gill" alt="Github" target="_blank">Amar-Gill</a></p>
		<p><strong>LinkedIn</strong> <a href="https://www.linkedin.com/in/amar-s-gill-65860662/" alt="LinkedIn"
				target="_blank">Amar Gill</a></p>
	</BasicCard>


	<BasicCard>
		<h2>Skills</h2>
		<p><strong>JavaScript</strong> React, Jest, Node, Express, JQuery, Typescript, Svelte, Sapper</p>
		<p><strong>Python</strong> Flask, Anaconda3, Pytorch, iPython, Jupyter Notebook, Spyder, Kivy</p>
		<p><strong>Mobile Development</strong> Flutter, Dart</p>
		<p><strong>Development Methodologies</strong> Test Driven Development, Mobile Responsiveness, RESTful APIs,
			Agile,
			RabbitMQ message brokering</p>
		<p><strong>Blockchain</strong> Solidity smart contracts, Truffle Suite, Web3, Metamask</p>
		<p><strong>Databases</strong> PostgreSQL, MongoDB, Cloud Firestore</p>
		<p><strong>Cloud Infrastructure</strong> Heroku, AWS S3, Firebase</p>
		<p><strong>eCommerce</strong> Braintree, SendGrid</p>
	</BasicCard>

	<BasicCard>


		<h2>Work History</h2>
		<p><strong>Morrison Hershfield Ltd. (2017-2019)</strong> Building science consulting and contract administration
			services for building owners, operators, product manufacturers and regulatory compliance (LEED, Passive
			House)
		</p>
		<p><strong>Voith Hydro GmbH (2016-2017)</strong> Leading scrum meetings, budget estimation, submittals tracking
		</p>
		<p><strong>Ontario Power Generation (2014-2015)</strong> Project management oversight for a $3 million domestic
			waterline replacement project</p>
	</BasicCard>

	<BasicCard>
		<h2>Personal Projects</h2>
		<p><strong>Learning Quest [Svelte, Sapper, Firebase, Firestore]</strong></p>
		<ul>
			<li>Interactive self guided education tool for children</li>
			<li>Can be accessed through this <a href="https://learning-quest.now.sh/" target="_blank"
					alt="learning quest">link</a></li>
		</ul>
		<p><strong>Leet Quiz [Flutter, Firebase, Firestore]</strong></p>
		<ul>
			<li>A mobile quiz game where users answer questions on a variety of topics related to web and mobile
				development
			</li>
			<li>Implemented a Firestore NoSQL database to save user progress and Firebase authentication for Google and
				Apple accounts</li>
			<li>Available for download in <a href="https://www.apple.com/ios/app-store/" alt="apple app store"
					target="_blank"> Apple App Store</a> and <a
					href="https://play.google.com/store/apps/details?id=dev.amar.quizdemo" alt="play store"
					target="_blank">Google Play Store</a></li>
		</ul>
	</BasicCard>

</section>