# Title: Tłumaczenie wtyczki
<!-- Position: 1 -->
---
Każdy plugin posiada folder o nazwie `languages`, w którym znajdują się różne pliki językowe dla każdego języka.

```
/bl-plugins/<PLUGIN_NAME>/languages/
	de_DE.json
	en.json
	es.json
	fr_FR.json
	...
```

<div class="note">
<div class="title">Kodownaie plików</div>
Format kodowania plików <b>JSON</b> to <b>UTF-8</b>.
</div>

---

To jest prosty przykład zaczerpnięty z języka angielskiego, pliku `en.json`. Każda linia w tym pliku zawiera parę klucz-wartość. Klucz występuje po stronie lewej, wartość po prawej.

<pre><code data-language="JSON">{
	"plugin-data":
	{
		"name": "Page list",
		"description": "Shows the list of pages in order."
	},

	"home": "Home",
	"show-home-link": "Show home link"
}</code></pre>

Jak widać, mamy do czynienia z polem zwanym `plugin-data`, w którym występuje nazwa oraz opis tej wtyczki. Kolejne pola w tym tłumaczeniu to frazy `home` oraz `show-home-link`.

A teraz to samo, po hiszpańsku z plikiem `es.json`.

<pre><code data-language="JSON">{
	"plugin-data":
	{
		"name": "Listado de paginas",
		"description": "Muestra el listado de paginas en orden."
	},

    "home": "Inicio",
    "show-home-link": "Mostrar link de la pagina de incio"
}</code></pre>
