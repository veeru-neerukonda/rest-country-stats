<script>
    import {createEventDispatcher} from 'svelte';
    import Icon from '@iconify/svelte';

    const dispatch = createEventDispatcher();
    let text;
</script>

<div class="search">
    <div class="search__icon-wrapper">
        <Icon width="24" height="24" icon="carbon:search" />
    </div>
    <input class="search__field h--04" type="text" on:input={()=>{dispatch('text:changed',text)}} bind:value={text} placeholder="Search For A Country">
</div>

<style lang="scss">
    .search{
        display: inline-block;
        position: relative;
        
        &__icon-wrapper{
            position: absolute;
            left: 1.6rem;
            top: 50%;
            transform: translateY(-50%);
            color: var(--color-text);
        }


        &__field{
            width: 100%;
            padding-top: var(--spacing-05);
            padding-bottom: var(--spacing-05);
            padding-left: 5.6rem; //1.6rem padding + 2.4rem icon size
            padding-right: var(--spacing-09);

            background-color: var(--color-foreground);
            color: var(--color-text);
            border: none;
            border-radius: .5rem;
        }

        &__field:focus{
            outline: 3px solid var(--color-selection);
        }
    }
</style>