# Meta tags en script imports
Voor het maken van het tentamen heb je soms imports nodig van bestanden voordat deze werken.

## Meta tag responsive view
Om de website responsive te maken heb je een meta tag nodig, bijvoorbeeld het volgende:
```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
Daarnaast moet je in de css een media query maken, bijvoorbeeld het volgende:
```
@media only screen and (max-width: 800px) {
  .className {
    width: 500px;
  }
}
```

## Script tags importeren
Door een script tag te importeren gebruik je de volgende code:
```
<script src="./js/index.js"></script>
```
Het kan ook zijn dat de script niet wordt geladen of niet op tijd. Je kunt dan ```defer``` er voor zetten, dan wordt het script na dat de hele website is geladen ingeladen.
```
<script defer src="./js/index.js"></script>
```
## Script modules
Bij het importeren van script modules moet je de type ```module``` mee geven. Dit doe je door ```type="module"```, zoals hier onder:
```
<script type="module" src="./js/index.js"></script>
```
