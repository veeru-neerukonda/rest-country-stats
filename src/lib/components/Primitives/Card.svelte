<script>
    let modifierCssClasses;
    export {modifierCssClasses as class};
</script>

<div class={`card ${modifierCssClasses}`}>
    <slot></slot>
</div>

<style lang="scss">
    .card{
        background-color: var(--color-foreground);
        color: var(--color-text);

        &--padding-05{
            padding: var(--spacing-05);
        }
    }
</style>