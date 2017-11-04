# Title: Podstawy
<!-- Position: 1 -->
---
Motywy w Bludit są bardzo elastyczne, dzięki czemu możesz wybrać dowolny framework ([Bootstrap](http://getbootstrap.com/), [Kube](http://imperavi.com/kube/), [Pure.io](purecss.io), [Skel](https://github.com/n33/skel), [Less](http://lesscss.org/), etc), dowolony kod Javascript, cokolwiek innego, aby zbudować swój motyw.

Wszystkie motywy znajdują się w katalogu `bl-themes` i mają zdefiniowaną strukturę.

### Spis treści
1. [Struktura motywu](#structure)
2. [Informacje o motywie](#information)
3. [Nazwa i opis](#name-description)

---

## <a id="structure"></a> Struktura motywu
Tak wygląda prosta, obowiązkowa struktura folderów i plików dla motywów.
```
/bl-themes/{THEME_NAME}/
	language/en.json
	metadata.json
	index.php
```

## <a id="information"></a> Informacje o motywie
Informacje dotyczące motywu znajdują się w pliku JSON o nazwie `metadata.json`.
<pre><code data-language="JSON">{
	"author": "Bludit",
	"email": "",
	"website": "https://themes.bludit.com",
	"version": "2.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}</code></pre>

## <i id="name-description"></i> Nazwa i opis
Informacje dotyczące motywu znajdują się w pliku JSON o nazwie `languages/en.json`.
<pre><code data-language="JSON">{
	"theme-data":
	{
		"name": "Witaj, świecie",
		"description": "Mój nowy motyw"
	}
}</code></pre>

<div class="note">
<div class="title">Przykłady</div>
Odwiedź nasze repozytorium w serwisie Github, aby rzucić okiem na <a href="https://github.com/bludit/examples">więcej przykładów</a>.
</div>