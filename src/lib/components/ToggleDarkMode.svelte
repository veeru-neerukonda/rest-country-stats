<script>
    import {createEventDispatcher} from 'svelte';
    import Icon from '@iconify/svelte';

    const dispatch = createEventDispatcher();

    let darkMode = false;
    function clickHandler(){
        darkMode = !darkMode;
        let html = document.querySelector('html');
        if(darkMode === true)
        {
            html.dataset.theme = "dark";
        }
        else if(darkMode === false)
        {
            html.dataset.theme = "light";
        }
        else{
            console.log('darkMode variable inside the ToggleDarkMode Component is not set to a boolean value');
        }
        dispatch('dark-mode:toggle',darkMode)
    }
</script>

<div class="toggle-dark-mode" on:click={clickHandler}>
    {#if darkMode === false}
        <Icon icon="bi:moon" width="24" height="24"/>
    {:else}
        <Icon icon="bi:moon-fill" width="24" height="24"/>
    {/if}
    <h1 class="toggle-dark-mode__heading">Dark Mode</h1>
</div>

<style lang="scss">
    .toggle-dark-mode{
        display: flex;
        column-gap: var(--spacing-03);
        align-items: center;
        cursor: pointer;

        &__heading{
            font-family: 'Nunito Sans', sans-serif;
            font-style: normal;
            font-weight: 600;
            font-size: 2rem;
            line-height: 2.7rem;
            text-align: center;

            color: var(--text-color);
        }
    }
</style>