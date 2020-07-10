<style>
    div {
        max-width: 56rem;
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

    div :global(a) {
        color: var(--hue-3);
    }

    div :global(a:visited) {
        color: var(--compliment-1);
    }
</style>

<div>
    <slot></slot>
</div>