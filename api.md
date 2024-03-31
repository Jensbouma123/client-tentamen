# client-tentamen
Hulp repository voor client tentamen.


### Maken van een custom api class 
In de volgende klasse kun je gemakkelijk een api call maken. Maak een bestand aan genaamd <b>api.js</b> en voeg de onderstaande code toe.
```
export default class api {
    headers;
    constructor() {
        this.headers = {
            "Content-Type": "application/json"
        };
    }

    post = async (url, body, headers) => {
        let data = body;
        if(typeof data !== "object") {
            data = {body}
        }
        try {
            const response = await fetch(url, {
                headers: headers ? headers : this.headers,
                method: "POST",
                body: JSON.stringify(data),
            });
            return response;
        } catch (error) {
            console.error("Error:", error);
            throw error;
        }
    }

    get = async (url, headers) => {
        try {
            const response = await fetch(url, {
                headers: headers ? headers : this.headers,
                method: "GET",
            });
            return response;
        } catch (error) {
            console.error("Error:", error);
            throw error;
        }
    }
}

```
De code kun je vervolgens importeren in andere bestanden door de volgende code bovenaan in je project te zetten.
```
import api from './api.js';
```
dan kun je <b>api</b> gebruiken om vervolgens een 'post' of 'get' request mee te doen.

```
// Post request met verstuurde data
api.post("https://localhost:3000", {
    value: "Verstuurde waarde",
});

// Get request
api.get("https://localhost:3000");
