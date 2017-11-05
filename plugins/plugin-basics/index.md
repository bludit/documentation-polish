# Title: Podstawy
<!-- Position: 1 -->
---
Wtyczki w Bludit znajdują się w katalogu `bl-plugins` o zdefiniowanej skrukturze. W Bludit, każda wtyczka jest obiektem ze zdefiniowanymi hakami (metodami).

### Spis treści
1. [Wtyczka Hello World](#hello-world)
2. [Struktura wtyczki](#structure)
3. [Informajce o wtyczce](#information)
4. [Nazwa i opis](#name-description)

---

## <i id="hello-world"></i> Hello World
Wtyczka Hello World dla Bludit.
<pre><code data-language="php"><?php
	class pluginHello extends Plugin {
		public function siteSidebar() {
			echo 'Hello world';
		}
	}
?></code></pre>

## <i id="structure"></i> Plugins structure
Tak wygląda obowiązkowa struktura folderów i plików dla wtyczek.
```
/bl-plugins/{PLUGIN_NAME}/
	language/en.php
	metadata.json
	plugin.php
```

## <i id="information"></i> Informacje o wtyczce
Wszystkie informacje znajdują się w pliku JSON `metadata.json`.
<pre><code data-language="JSON">{
	"author": "Bludit",
	"email": "",
	"website": "https://plugins.bludit.com",
	"version": "2.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}</code></pre>

## <i id="name-description"></i> Nazwa i opis
Nazwa i opis znajdują się w pliku JSON `languages/en.json`.
<pre><code data-language="JSON">{
	"plugin-data":
	{
		"name": "Hello World",
		"description": "Print Hello World in the sidebar"
	}
}</code></pre>

<div class="note">
<div class="title">Przykłady</div>
Odwiedź nasze repozytorium w serwisie Github, aby rzucić okiem na <a href="https://github.com/bludit/examples">więcej przykładów</a>.
</div>