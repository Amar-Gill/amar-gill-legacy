<script>
</script>

<style>
    a,
    a:visited {
        color: aqua;
    }
    section {
        --contentHeight: 35vh;
        width: 38vw;
        margin: auto;
        background-color: black;
        color: var(--text);
        margin: 1.5rem auto auto 1.5rem;
    }

    details > summary {
        cursor: pointer;
        list-style-type: none;
        font-size: 1.5rem;
        border-bottom: solid 2px;
    }

    details > summary > svg {
        /*   color: green; */
        transition: transform 1.5s;
        transform: rotate(0deg);
    }

    details > div {
        overflow: auto;
    }

    details[open] > div {
        animation-name: slideDown;
        animation-duration: 0.8s;
        animation-fill-mode: forwards;
    }

    /* rotate wheel */
    details[open] > summary > svg {
        transition: transform 1.5s;
        transform: rotate(180deg);
    }

    details[open] > div > * {
        opacity: 0;
        animation-name: showContent;
        animation-duration: 0.6s;
        animation-delay: 0.2s;
        animation-fill-mode: forwards;
    }

    @keyframes slideDown {
        from {
            opacity: 0;
            max-height: 0;
        }
        to {
            opacity: 1;
            max-height: var(--contentHeight);
        }
    }

    @keyframes showContent {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }

    @media only screen and (max-width:451px) {
        section {
            width: 90vw;
            margin: 1.5rem auto auto auto;
        }
    }
</style>

<svelte:head>
    <title>Home</title>
</svelte:head>
<section>
    <details>
        <summary>
            <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="feather feather-hexagon"><path
                    d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z" /></svg>
            Summary
        </summary>
        <div>
            <p>
                My name is Amar, and I am a web developer based out of Toronto,
                Canada. After earning a degree in Civil Engineering and working
                in
                <a href="/past_career"> construction and development </a>
                for some time, I took the leap to learn software development and
                haven't looked looked back.
            </p>
            <div>
                <a
                    href="https://github.com/Amar-Gill"
                    target="_blank"
                    title="Github profile"
                    alt="github">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="44"
                        height="44"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="white"
                        stroke-width="1.5"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        class="feather feather-github"><path
                            d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22" /></svg>
                </a>
                <a
                    href="https://www.linkedin.com/in/amar-s-gill-65860662/"
                    target="_blank"
                    title="LinkedIn profile"
                    alt="linkedin">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="44"
                        height="44"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="white"
                        stroke-width="1.5"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        class="feather feather-linkedin"><path
                            d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z" />
                        <rect x="2" y="9" width="4" height="12" />
                        <circle cx="4" cy="4" r="2" /></svg>
                </a>
                <a
                    href="mailto:amar.s.gill@outlook.com"
                    alt="email"
                    title="Send me an email">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="44"
                        height="44"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="white"
                        stroke-width="1.5"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        class="feather feather-mail"><path
                            d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z" />
                        <polyline points="22,6 12,13 2,6" /></svg>
                </a>
                <a
                    href="/resume.pdf"
                    target="_blank"
                    alt="resume"
                    title="Resume">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="44"
                        height="44"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="white"
                        stroke-width="1.5"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        class="feather feather-file-text"><path
                            d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z" />
                        <polyline points="14 2 14 8 20 8" />
                        <line x1="16" y1="13" x2="8" y2="13" />
                        <line x1="16" y1="17" x2="8" y2="17" />
                        <polyline points="10 9 9 9 8 9" /></svg>
                </a>
            </div>
        </div>
    </details>

    <details>
        <summary>
            <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="feather feather-hexagon"><path
                    d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z" /></svg>
            Projects
        </summary>
        <div>
            <p>
                <a
                    href="https://learning-quest.now.sh"
                    target="_blank"
                    alt="learning quest">
                    Learning Quest
                </a>
                <a
                    href="https://github.com/Amar-Gill/learning-quest"
                    target="_blank"
                    alt="learning quest source">
                    [source]
                </a>
            </p>

            <ul>
                <li>Interactive self guided education tool for children</li>
            </ul>
            <p>
                <a
                    href="https://play.google.com/store/apps/details?id=dev.amar.quizdemo&hl=en"
                    target="_blank"
                    alt="leet quiz">
                    Leet Quiz
                </a>
                <a
                    href="https://github.com/Amar-Gill/flutter-quizapp"
                    target="_blank"
                    alt="learning quest source">
                    [source]
                </a>
            </p>
            <ul>
                <li>
                    Quiz style game about various topics within web and mobile
                    development
                </li>
                <li>
                    Available for download in Apple App Store and Google Play
                    Store
                </li>
            </ul>
        </div>
    </details>

    <details>
        <summary>
            <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="feather feather-hexagon"><path
                    d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z" /></svg>
            Open Source
        </summary>
        <div>
            <ul>
                <li>
                    Issue
                    <a
                        href="https://github.com/sveltejs/svelte/issues/5421"
                        alt="issue-number"
                        target="_blank">#5421</a>
                    for the Svelte UI framework
                </li>
            </ul>
        </div>
    </details>

    <details>
        <summary>
            <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="feather feather-hexagon"><path
                    d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z" /></svg>
            Legal
        </summary>
        <div>
            <p>
                Applications distributed through publicly available channels may
                collect email addresses. This is to enable authentication of
                users of the application and for gathering usage statistics for
                product development purposes. User data will remain anonymous
                and will not be sold to third parties for the purposes of
                marketing or advertising.
            </p>
        </div>
    </details>
</section>
