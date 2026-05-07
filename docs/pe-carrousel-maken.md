# Workshop - PE Carrousel in SvelteKit

## PE Carroussel maken

Met CSS en JavaScript ga je de carrousel stapje voor stapje enhancen.

### Aanpak

#### 1. Kopieer CSS
Kopieer in je code editor de CSS uit [voorbeeld.css](voorbeeld.css) in een `<style> ... </style>` element onderaan in  `> src > routes > +page.svelte`

```css
<style>
/* Plak de gekopieerde CSS hieronder*/

</style
```
#### 2. Uncomment @layers
Alle voorbeeld CSS staat in comments. Haal per `@layer` van boven naar beneden de comments weg en bekijk telkens in de **Chrome** browser wat er verandert aan de Carrousel. Elke CSS layer is een extra enhancement. Bekijk het eindresultaat ook in de **Firefox browser*. Werken daar ook alle enhancements?

#### 3. Voeg onMount functie toe
Voor browsers die de `::scroll-button(*)` selector in CSS nog niet ondersteunen, kunnen we de HTML `button` elementen interactief maken met 'JavaScript'

Om in een Svelte component toegang te kunnen krijgen tot de `DOM` en dus tot deze HTML `button` elementen,  heb je de `onMount` functie nodig.

Voeg onderstaande code toe aan het `<script> ... </script>` element bovenaan het  `> src > routes > +page.svelte` component.

```javascript
<script>
  import { onMount } from "svelte";

  let { data } = $props();

  onMount(() => {
    // Plak de gekopieerde JavaScript hieronder
    
  });

</script>
```

#### 4. Kopieer JavaScript
Kopieer in je code editor de JavaScript uit [voorbeeld.js](voorbeeld.js) in de `onMount` functie. Bekijk nu nog eens in de **Firefox** browser de Carrousel. Zijn er nu wel vorige en volgende buttons? En werken ze?

<hr>
Ga verder met de volgende stap: [Website live zetten met Netlify](https://github.com/fdnd-task/workshop-pe-carrousel-in-sveltekit/edit/main/docs/website-live-zetten-met-netlify.md)








