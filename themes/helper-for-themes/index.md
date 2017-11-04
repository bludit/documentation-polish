# Title: Pomoce dla motywów
<!-- Position: 100 -->
---

Pomoce dla motywów pozwalają deweloperom tworzyć motywyThis helper tries to help developers by making them write less code and keep it more clean.

Ten obiekt zawiera statyczne metody.

## Tytuł
Generuje tag `<title>` w sekcji head Twojej strony łącznie z nazwą wyświetlanej witryny.
<pre><code data-language="php"><?php
	echo Theme::headTitle();
?></code></pre>

```
<title>Nazwa strona | Nazwa witryny</title>
```

## Opis
Generuje tag `<description>` w sekcji head z opisem dołączonym do wyświetlanej strony lub ustawionym w ustawieniach głównych.
<pre><code data-language="php"><?php
	echo Theme::headDescription();
?></code></pre>

```
<meta name="description" content="Opis Twojej strony...">
```

## Pliki CSS
Generuje w sekcji head ścieżkę motywu do pliku ze stylami `blog.css` z katalogu `/bludit/themes/{TWÓJ_MOTYW}/css/`.
<pre><code data-language="php"><?php
	echo Theme::css('css/blog.css');
?></code></pre>

```
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/blog.css">
```

... lub w przypadku wielu plików tego samego typu:
<pre><code data-language="php"><?php
	echo Theme::css(array('css/file1.css', 'css/file2.css'));
?></code></pre>

```
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/file1.css">
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/file2.css">
```

## Pliki Javascript
Generuje w sekcji head ścieżkę motywu do pliku ze skryptami `main.js` z katalogu `/bludit/themes/{THEME_NAME}/js/`.
<pre><code data-language="php"><?php
	echo Theme::js('js/main.js');
?></code></pre>

```
<script src="https://example.com/bl-themes/{THEME_NAME}/js/main.js"></script>
```

... lub w przypadku wielu plików tego samego typu:
<pre><code data-language="php"><?php
	echo Theme::js(array('js/file1.js', 'js/file2.js'));
?></code></pre>

```
<script src="https://example.com/bl-themes/{THEME_NAME}/js/file1.js"></script>
<script src="https://example.com/bl-themes/{THEME_NAME}/js/file2.js"></script>
```

## Favicon
Generuje w sekcji head ścieżkę do ikony favicon, który w tym wypadku znajduje się w głównym katalogu motywu `/bludit/themes/{THEME_NAME}/favicon.png`.

<pre><code data-language="php"><?php
	echo Theme::favicon('favicon.png');
?></code></pre>

```
<link rel="shortcut icon" href="https://examples.com/bl-themes/{THEME_NAME}/favicon.png" type="image/png">
```

## Dołączanie pluginów
Każda wtyczka posiada tzw. haki, dzięki czemu możesz umieścić te wtyczki w dowolnym miejscu motywu.

Dla przykładu, dołączanie wtyczek z hakami do sekcji head.
<pre><code data-language="php">
<head>
...
<?php
	Theme::plugins('siteHead');
?>
...
</head>
</code></pre>

Dołączanie wtyczek z hakami do sekcji body.
<pre><code data-language="php">
<body>
<?php
	Theme::plugins('siteBodyBegin');
?>
...
</body>
</code></pre>

## Dołączanie jQuery
Bludit korzysta z [jQuery](http://jquery.com) i wprowadza metodę dołączania go do motywów.

<pre><code data-language="php"><?php
	echo Theme::jquery();
?></code></pre>

```
<script src="https://example.com/bl-kernel/js/jquery.min.js"></script>
```

... lub dodaj [jQuery](http://jquery.com) z oficjalnego kanału CDN.

<pre><code data-language="php"><?php
	$cdn = true;
	echo Theme::jquery($cdn);
?></code></pre>

```
<script src="https://code.jquery.com/jquery-3.2.1.min.js" integrity="sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=" crossorigin="anonymous"></script>
```

## Dołączanie FontAwesome
Bludit korzysta z [FontAwesome](http://fontawesome.io) wprowadza metodę dołączania go do motywów.

<pre><code data-language="php"><?php
	echo Theme::fontAwesome();
?></code></pre>

```
<link rel="stylesheet" href="https://example.com/bl-kernel/css/font-awesome/css/font-awesome.min.css">
```

... lub dodaj [FontAwesome](http://fontawesome.io) z oficjalnego kanału CDN [BootstrapCDN](https://www.bootstrapcdn.com)

<pre><code data-language="php"><?php
	$cdn = true;
	echo Theme::fontAwesome($cdn);
?></code></pre>

```
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">
```
