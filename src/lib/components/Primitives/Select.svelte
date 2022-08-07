<script>
    import Icon from '@iconify/svelte';

    export let items = [
        {
            value: "Africa",
            name: "Africa"
        },
        {
            value: "America",
            name: "America"
        },
        {
            value: "Asia",
            name: "Asia"
        },
        {
            value: "Europe",
            name: "Europe"
        },
        {
            value: "Oceania",
            name: "Oceania"
        }
    ];

    let isOpen = false;
    let selectValue = "";

    let display;
</script>

<div class="select" tabindex="0">
    <input bind:this="{display}" class="select__display h--04" type="text" value="Hanna" on:click={()=>{isOpen = !isOpen}}>
    <div class="select__icon-wrapper">
        <Icon width="24" height="24" icon="ep:arrow-down" />
    </div>
    {#if isOpen === true}
        <div class="select__list">
            {#each items as item,index (index)}
                <h4 
                    class="select__item h--04"
                    class:select__item-selected={item.value === selectValue}
                    on:click={()=>{
                        selectValue = item.name;
                        display.value = selectValue;
                        isOpen = !isOpen;
                    }}
                >
                    {item.name}
                </h4>
            {/each}
        </div>
    {/if}
</div>

<style lang="scss">
    .select{
        display: inline-block;
        position: relative;
        color: var(--color-text);

        &__display{
            caret-color: transparent;
            width: 100%;
            padding: var(--spacing-05);
            
            border: none;
            border-radius: .5rem;
            background-color: var(--color-foreground);

            cursor: pointer;
        }

        &__display:focus{
            outline: 3px solid var(--color-selection);
        }

        &__icon-wrapper{
            position: absolute;
            right: 1.6rem;
            top: 50%;
            transform: translateY(-50%);

            cursor: pointer;
            pointer-events: none;
        }

        &__list{
            position: absolute;
            bottom: -1rem;
            transform: translateY(100%);

            border-radius: 5px;

            display: flex;
            flex-direction: column;
            row-gap: var(--spacing-03);

            width: 100%;
            padding: var(--spacing-05);
            background-color: var(--color-foreground);
        }

        // &__display:focus ~ &__list{
        //     display: flex;
        // }

        &__item{
            transition: all 0.2s;
            background-color: var(--color-foreground);
            width: 100%;

            cursor: pointer;
        }

        &__item-selected,
        &__item:hover{
            background-color: var(--color-background);
            padding-left: var(--spacing-03);
        }
    }
</style>