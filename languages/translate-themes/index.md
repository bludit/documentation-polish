# Title: Translate a theme
<!-- Position: 2 -->
---
Każdy motyw posiada folder o nazwie `languages`, w którym znajdują się różne pliki językowe dla każdego języka.

```
/bl-themes/{THEME_NAME}/languages/
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
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple and clean, based on the framework Pure.css."
	}
}</code></pre>

Jak widać, mamy do czynienia z polem zwanym `theme-data`, w którym występuje nazwa oraz opis tego motywu.

A teraz to samo, po hiszpańsku z plikiem `es.json`.

<pre><code data-language="JSON">{
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple y minimalista, basado en el framework Pure.css."
	}
}</code></pre>
