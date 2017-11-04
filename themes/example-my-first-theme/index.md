# Title: Example: Mój pierwszy motyw
<!-- Position: 2 -->
---
Stwórzmy teraz pierwszy, prosty motyw i nazwijmy go `Coffee`.

- Utwórz nowy folder wewnątrz katalogu `/bl-themes/`, otrzymasz wtedy ścieżkę `/bl-themes/coffee/`
- Utwórz folder `languages`, wewnątrz `/bl-themes/coffee/`
- Utwórz plik `en.json` wewnątrz `/bl-themes/coffee/languages/`
- Utwórz plik `metadata.json` wewnątrz `/bl-themes/coffee/`
- Utwórz plik `index.php`, wewnątrz `/bl-themes/coffee/`

Struktura folderów i plików powinna być więc taka:
```
/bl-themes/coffee/
	language/en.json
	metadata.json
	index.php
```

Kolejnym krokiem będzie wypełnienie plików o stosowną zawartość zaczynając od pliku `index.php` umieść następujący kod HTML i PHP.
<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>Bludit</title>
</head>
<body>
	<?php foreach ($pages as $Page): ?>

	<h1><?php echo $Page->title() ?></h1>
	<div><?php echo $Page->content() ?></div>

	<hr>

	<?php endforeach; ?>
</body>
</html>
</code></pre>

Teraz w pliku `languages/en.json` umieść stosowne informacje dotyczące motywu.
<pre><code data-language="php">{
	"theme-data":
	{
		"name": "Coffee",
		"description": "This is my first theme for Bludit."
	}
}
</code></pre>

Teraz w pliku `metadata.json` uzupełnij bardziej szczegółowe informacje dotyczące motywu.
<pre><code data-language="php">{
	"author": "Bludit",
	"email": "",
	"website": "",
	"version": "1.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}
</code></pre>

Gratulacje, Twój pierwszy motyw jest już gotowy!

<div class="note">
<div class="title">Przykłady</div>
Odwiedź nasze repozytorium w serwisie Github, aby rzucić okiem na <a href="https://github.com/bludit/examples">więcej przykładów</a>.
</div>