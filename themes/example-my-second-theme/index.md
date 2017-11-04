# Title: Example: Mój drugi motyw
<!-- Position: 3 -->
---
## 1. Struktura katalogu
Stwórzmy teraz odpowiednią strukturę katalogów dla tego motywu. Motyw ten nazwijmy `Mars`.
Utwórz folder motywu w katalogu `/bl-themes/`, otrzymasz wtedy ścieżkę `/bl-themes/mars/`.

Następnie, utwórz foldery dla języków, stylów css i plików js:
- Utwórz folder `languages` wewnątrz `/bl-themes/mars/`
- Utwórz folder `css` wewnątrz `/bl-themes/mars/`
- Utwórz folder `js` wewnątrz `/bl-themes/mars/`

```
/bl-themes/mars/
	css/
	js/
	language/
```

## 2. Informacje o motywie
Utwórz plik zawierający szczegółowe informacje o motywie. Plik ten powinien znajdować się w głównym katalogu motywu o nazwie `metadata.json` i zawartością:

```
{
	"author": "Bludit",
	"email": "",
	"website": "",
	"version": "1.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}
```

Teraz należy utworzyć plik z nazwą i opisem motywu; o nazwie `en.json` wewnątrz katalogu `/bl-themes/mars/languages/`, zawierający:

```
{
	"theme-data":
	{
		"name": "Mars",
		"description": "This is my second theme for Bludit."
	}
}
```

## 3. index.php
Popracujmy nad plikiem głównym `index.php`, który należy utworzyć wewnątrz folderu `/bl-themes/mars/`, z następującą zawartością:

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
</head>
<body>

</body>
</html>
</code></pre>

### 3.1. Pliki CSS
Dodaj pliki CSS, możesz użyć gotowych poleceń tj. `Theme::` lub tagu `link`. W tym wypadku posłużymy się poleceniem, które wprowadzi plik css `blog.css`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>
</head>
<body>

</body>
</html>
</code></pre>

### 3.2. Pliki JavaScript
Dodaj pliki JavaScript, możesz użyć gotowych poleceń tj. `Theme::` lub tagu `script`. Podobnie jak przy plikach CSS, tutaj również posłużymy się poleceniem, które wprowadzi plik javascript `blog.js`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>
</head>
<body>

</body>
</html>
</code></pre>

### 3.3. Wtyczki z hakami siteHead
Krótki przykład umożliwiający dodanie do motywu obsługi wtyczek `Theme::plugins`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>

</body>
</html>
</code></pre>

### 3.4. Tytuł strony
Dodawanie tytułu strony do sekcji `body`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>
</body>
</html>
</code></pre>

### 3.5. Treść
Teraz popracujmy nad wyświetlaniem treści naszej strony.

Aby zlokalizować stronę, na której aktualnie się znajdujemy, do pomocy skorzystamy z wyrażenia `$WHERE_AM_I`. Na przykład, jeśli użytkownik przegląda pewną stronę, wyrażenie dla tej strony przyjmie wartość `page`, a dla strony głównej `home`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			echo 'The user is browsing the front page';
		}
		elseif ($Url->whereAmI()=='page') {
			echo 'The user is browsing a particular page';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>
</body>
</html>
</code></pre>

Jeśli użytkownik znajduje się na stronie głównej, Bludit automatycznie wygeneruje wszystkie opublikowane strony `$pages`, każda strona jest obiektem [Page Object](https://).

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			foreach ($pages as $Page) {
				echo '<h1>'.$Page->title().'</h1>';
				echo '<div>'.$Page->content().'</div>';
				echo '<hr>';
			}
		}
		elseif ($Url->whereAmI()=='page') {
			echo 'The user is browsing a particular page';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>
</body>
</html>
</code></pre>

Jeśli użytkownik znajduje się na konkretnej stronie, Bludit automatycznie wygeneruje obiekt `$Page`. Istnieje także wiele innych metod, ale my posłużymy się metodami `title()` oraz `content()`. Aby poznać inne metody, udaj się do strony [Page Object](http://).

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			foreach ($pages as $Page) {
				echo '<h1>'.$Page->title().'</h1>';
				echo '<div>'.$Page->content().'</div>';
				echo '<hr>';
			}
		}
		elseif ($Url->whereAmI()=='page') {
			echo '<h1>'.$Page->title().'</h1>';
			echo '<div>'.$Page->content().'</div>';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>
</body>
</html>
</code></pre>

### 3.6. Wtyczki w sekcji body
Aby zakończyć tworzenie podstawowego motywu, zapewnij mu jeszcze obsługę wtyczek w sekcji `body`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Plugins site body begin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			foreach ($pages as $Page) {
				echo '<h1>'.$Page->title().'</h1>';
				echo '<div>'.$Page->content().'</div>';
				echo '<hr>';
			}
		}
		elseif ($Url->whereAmI()=='page') {
			echo '<h1>'.$Page->title().'</h1>';
			echo '<div>'.$Page->content().'</div>';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>

	<!-- Plugins site body end -->
	<?php Theme::plugins('siteBodyEnd') ?>

</body>
</html>
</code></pre>

<div class="note">
<div class="title">Przykłady</div>
Odwiedź nasze repozytorium w serwisie Github, aby rzucić okiem na <a href="https://github.com/bludit/examples">więcej przykładów</a>.
</div>