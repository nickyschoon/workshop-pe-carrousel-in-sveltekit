<script>
const { data } = $props()
const characters = (data.swCharactersData.results)

</script>

<main>
<h1>Star Wars</h1>

<ul>
    {#each characters as character}
    <li>{character.name}</li>
    {/each}
</ul>

</main>

<style>
</style>
