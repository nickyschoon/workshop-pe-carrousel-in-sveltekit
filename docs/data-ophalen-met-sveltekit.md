# Workshop - PE Carrousel in SvelteKit

## Data ophalen met SvelteKit

Met behulp van SvelteKit ga je voor de carrousel data ophalen uit een REST API en renderen naar HTML.

### Aanpak
#### 0. Installeer Node.js
Installeer Node.js als je dat al niet hebt gedaan.

#### 1. Installeer SvelteKit in de folder van de door jou geforkte repository

**Maak een SvelteKit instantie aan:**  
Open de folder  in de terminal en voer onderstaande commando uit.  
`npx sv create`

Maak deze keuzes tijden het installeren:
- vul een . in bij 'Where would you like your project to be created?'
- minimal barebone
- no type checking
- add nothing (enter)
- npm

**Installeer npm packages:**  
`npm install`

**Open de web aplicatie:**  
`npm run dev -— -—open`

#### 2. Kopieer HTML
Kopieer in je code editor de HTML uit [voorbeeld.html](voorbeeld.html) naar `> src > routes > +page.svelte`
Bekijk de HTML in de browser.

#### 3. Haal JSON data op uit een REST API
Maak een `+page.server.js` bestand aan in `> src > routes`

En plak onderstaande code in dit bestand.

```javascript
export const load = async () => {
    const endpoint = 'https://fdnd.directus.app/items/fdnd_features'

    const response = await fetch(endpoint);
    const data = await response.json();

    return {
      features: data.data
    }
}
```

#### 4. Render de opgehaalde data in HTML

Kopieer onderstaande code naar `> src > routes > +page.svelte`

```javascript
<script>
  let { data } = $props();
</script>

<main>
  <header>
    <h1>Frontend Design & Development</h1>
    <p><em>2-jarige Associate Degree aan de HvA</em></p>
  </header>

  //bind the div container to the carrousel variable in the script section
  <div bind:this={carrousel}>
    {#each data.features as feature}
      <article>
        <h2>{feature.title}</h2>
        <blockquote>{feature.intro}</blockquote>
      </article>
    {/each}
  </div>
  

  <footer>
    <button type="button" hidden>← Vorige</button>    
    <button type="button" hidden>Volgende →</button>
  </footer>
</main>
```

#### 5. Extra opdracht: haal data op uit een REST API naar keuze
Je kan de super coole FDND features in de Carrousel tonen, maar nog toffer is om de inhoud naar je eigen hand te zetten 🚀

Kies zelf een REST API uit: https://github.com/public-api-lists/public-api-lists, en verwerk de data in de Carrousel. Hiervoor zal je ook de HTML moeten aanpassen.

#### 8. Commit & push wijzigingen via de GitHub Desktop app
Hiermee breng je jouw wijzigingen van jouw locale repository naar de online GitHub repository.

<hr>

Ga verder met de volgende stap: [PE Carrousel maken](https://github.com/fdnd-task/workshop-pe-carrousel-in-sveltekit/blob/main/docs/pe-carrousel-maken.md)




