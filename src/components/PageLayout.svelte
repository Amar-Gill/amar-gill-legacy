<style>
    div {
        /* max-width: 56rem; */
        padding-top: 1em;
        padding-left: 14rem;
        padding-right: 14rem;
    }

    @media (max-width: 835px) {
        div {
            padding-left: 1rem;
            padding-right: 1rem;
        }
    }

    div :global(a) {
        color: var(--hue-3);
        cursor:pointer;
    }

    div :global(a:visited) {
        color: var(--compliment-1);
    }
</style>

<div>
    <slot></slot>
</div>