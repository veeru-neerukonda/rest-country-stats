<script>
    import '$lib/scss/main.scss';
    import NavBar from '$lib/components/NavBar.svelte';
    import Search from '$lib/components/Primitives/Search.svelte';
    import Select from '$lib/components/Primitives/Select.svelte';
</script>

<NavBar></NavBar>
<div class="u-margin-y-07">
    <Search></Search>
</div>

<div class="u-margin-y-07">
    <Select></Select>
</div>
