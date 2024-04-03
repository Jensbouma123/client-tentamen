# Hoe maak je een webcomponent
Hier is een uitleg bestand voor het maken van een webcomponent.

## Aanmaken webcomponent
Bij het maken van een webcomponent moet je een nieuw bestand maken met ```<naam>.js```, bijvoorbeeld ```navbar.js``` zoals hier onder weergegeven:
```
class Navbar extends HTMLElement {
    // webcomponent body
}
```
Daarna moet je een constructor aanmaken, deze methode heet gewoon constructor.
```
class Navbar extends HTMLElement {
    constructor() {
        super();
    }
}
```
Om even wat te laten zien in de webcomponent kun je HTML toevoegen aan de webcomponent. Bijvoorbeeld zo:
```
class Navbar extends HTMLElement {
    constructor() {
        super();
        this.innerHTML = `
    <nav>
        <h1>Logo</h1>
        <ul>
            <li>
                <a href="/">Home</a>
            </li>
        </ul>
    </nav>
`
    }
}
```
Nu heb je een webcomponent gemaakt! Alleen kun je deze nog niet gebruiken. Want hij is nog niet gedefined. Dit moet je nog doen doormiddel van ```customElements.define()```, daarin zet je een eigen naam met een '-' er tussen en dan de naam van de klasse, zoals hieronder:
```
customElements.define("nav-bar", Navbar);
```
Uiteindelijk heb je dan een compleet bestand met de volgende code:
```
class Navbar extends HTMLElement {
    constructor() {
        super();
        this.innerHTML = `
    <nav>
        <h1>Logo</h1>
        <ul>
            <li>
                <a href="/">Home</a>
            </li>
        </ul>
    </nav>
`
    }
}

customElements.define("nav-bar", Navbar);
```
Als je dan het bestand hebt geïmporteerd in je HTML bestand kun je vervolgens de webcomponent gebruiken in je HTML bestand, zoals hier onder:
```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <script type="module" src="./navbar.js"></script>
</head>
<body>
    <nav-bar></nav-bar>
</body>
</html>
```
Om even te laten zien dat het werkt zie je hier onder de uitkomst:

<img width="847" alt="image" src="https://github.com/Jensbouma123/client-tentamen/assets/15966774/00f8a6cf-c574-4b17-bfea-14aec473f7eb">

