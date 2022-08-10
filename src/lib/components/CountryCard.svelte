<script>
    export let countryFlag = "https://flagcdn.com/cn.svg";
    export let countryName = "People's Republic Of China";
    export let population = "140,21,12,000";
    export let region = "Asia";
    export let capital = "Beijing";
</script>

<div class="country-card">
    <img class="country-card__image" src={countryFlag} alt={countryName}>
    <div class="country-card__content">
        <h2 class="country-card__heading h--02 u-margin-top-05 u-margin-bottom-06">{countryName}</h2>
        <div class="country-card__stats">
            <span class="country-card__stat">
                <h3 class="h--03 u-capitalize">population: </h3>
                <h4 class="h--04 u-capitalize">{population}</h4>
            </span>
            <span class="country-card__stat">
                <h3 class="h--03 u-capitalize">region: </h3>
                <h4 class="h--04 u-capitalize">{region}</h4>
            </span>
            <span class="country-card__stat">
                <h3 class="h--03 u-capitalize">capital: </h3>
                <h4 class="h--04 u-capitalize">{capital}</h4>
            </span>
        </div>
    </div>
</div>

<style lang="scss">
    .country-card{
        width: 25rem;
        border-radius: .5rem;
        overflow: hidden;
        cursor: pointer;
        padding-bottom: var(--spacing-08);
        background-color: var(--color-foreground);
        color: var(--color-text);

        &__image{
            display: flex;
            width: 100%;
        }

        &__content{
            margin-left:  var(--spacing-05);
            margin-right: var(--spacing-05);
        }

        &__stat{
            display: flex;
            justify-content: space-between;
        }
    }
</style>