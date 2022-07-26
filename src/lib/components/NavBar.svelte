<script>
import Card from './Card.svelte';
import ToggleDarkMode from './ToggleDarkMode.svelte';

</script>

<Card class="card--padding-05">
    <div class="nav-bar">
        <h1 class="nav-bar__heading">Where In The World?</h1>
        <ToggleDarkMode />
    </div>
</Card>

<style lang="scss">
    @import '../scss/base/mixins';
    .nav-bar{
        display: flex;
        justify-content: space-between;
        align-items: center;

        &__heading{
            font-family: 'Nunito Sans', sans-serif;
            font-style: normal;
            font-weight: 900;
            font-size: 1.6rem;
            line-height: 2.5rem;
            text-align: center;
            text-transform: capitalize;
            color: var(--color-text);

            @include respond-to('medium')
            {
                font-size: 2.4rem;
                line-height: 3.3rem;
            }            
        }
    }
</style>