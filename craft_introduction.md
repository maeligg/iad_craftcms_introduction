# Craft: Introduction

## Craft

[Craft](http://buildwithcraft.com/) est un CMS récent créé par [Pixel & Tonic](http://pixelandtonic.com/). Craft est développé à l'aide de technologies open source comme PHP et MySQL et s'appuie sur un framework PHP qui a fait ses preuves: [Yii](http://www.yiiframework.com/).

Comparé à d'autres produits, Craft est axé sur l'essentiel: définir et gérer vos contenus, et ce de la façon la plus modulaire et flexible possible. Si vous avez besoin d'un moteur de commentaires, d'un forum ou encore d'e-commerce, il faudra vous tourner vers des plugins.

### Un modèle de pricing modulaire

Cette flexibilité est présente jusque dans [le pricing](http://buildwithcraft.com/pricing) du produit lui même. La version gratuite de Craft vous permet de développer facilement des sites assez simples en terme de data structure. D'autres fonctionnalités (différentes sections, différents utilisateurs, support cloud, support multilingue) peuvent être ajoutées via l'achat de packages disponibles dans le contexte de l'application elle-même. 

Cela vous permet en tant que développeur de ne payer que ce pour ce dont vous avez vraiment besoin, chaque projet ayant donc sa propre version particulière de Craft. Classiquement, si vous allez au delà d'un blog ou d'un portfolio, vous aurez besoin de Users (149 $) et Publish Pro (149 $).

### Atouts

Les principaux atouts de Craft sont à mon sens:

- Une flexibilité dans la définition de votre data structure rarement égalée. Les 16 field types disponibles par défaut permettent une approche extrêmement modulaire.
- [L'utilisation de Twig comme language de templating](http://twig.sensiolabs.org/doc/templates.html): cela induit un temps d'apprentissage mais les gains en termes de puissance, de modularité et de flexibilités sont étonnants. Toute la puissance et la maturité de Twig sont au services de vos templates.
- Une quantité impressionnantes de fonctionnalités qui rendront la vie de vos clients plus facile: live preview, control panel responsive, one click updates, etc.
- Un découplage important entre votre structure de dossiers et de fichiers et la manière dont sont construites les URL. La structure de vos URL est donc extrêmement flexible.
- Une solution intégrée pour les sites multilingues.

## Définir et structurer votre projet

Comme dit plus haut, Craft vous permet de structurer les données de votre site de façon extrêmement flexible et modulaire.

#### Sections, Entries et entry types

Dans Craft, vos contenus vont principalement "vivre" dans des entries, elles-même contenues dans des sections.

La data structure de ces entries va être déterminée par les custom fields que vous ajouterez à ces sections. Pour chaque entry type dans Craft, vous pouvez créer un field layout qui va préciser quels fields vont être utilisés pour définir les entries de cette section.

Il y a [trois grands types de sections](http://buildwithcraft.com/docs/sections-and-entries) dans craft: channel, structure et single.

##### Sections de type channel

Ces sections contiennent un ensemble d'entries que vous pouvez ensuite classer et afficher de diverses façons à l'aide de vos templates.

Pour chaque section de ce type, vous pouvez spécifier un pattern d'URL qui sera appliqué à toutes les entries de cette section.

Les sections de type channel peuvent contenir différents types d'entries ("entry types") avec des data structure différentes. Créer un blog permettant de poster divers types de contenus est donc très facile. Vous n'avez besoin que d'une seule section avec différents types d'entrées (video, post, son, gallérie photo, etc.). 

L'entry type peut facilement être utilisé [dans le routing et les patterns d'URL](http://buildwithcraft.com/help/entry-type-urls), comme [dans vos tags craft.entries et vos tests conditonnels](http://buildwithcraft.com/docs/templating/entrymodel#type)

##### Sections de type single

Ces sections contiennent une seule entry et sont utilisées pour les pages particulières de votre site, comme par exemple une page "about" ou votre "homepage". Utiliser une section de type single vous permet de bénéficier de tous vos custom fields pour définir les contenus de cette page.

Vous pouvez également définir vous même l'URL de l'entry contenue dans chacune de ces sections de type single, ainsi que le template à utiliser pour le rendu.

##### Sections de type structures

Les sections de type structure ressemblent beaucoup aux sections de type channel: elles peuvent avoir plusieurs entry types et les patterns d'URL des entries qu'elles contiennent peuvent être précisés.

La grande différence est que ces sections de type structure sont destinées à créer des agencements hiérarchiques d'entries dont l'ordre peut être modifié. Vous pouvez ainsi préciser le nombre de niveaux possibles dans cette hiérarchie d'entries, les patterns d'URL à différents niveaux dans votre hiérarchie, le template à utiliser pour le rendu des entries, etc.

#### Fields, Field Groups et Field Layouts

Craft vous propose [16 types de champs](http://buildwithcraft.com/docs/fields) à l'aide desquels vous pouvez définir la data structure de vos entries.

Dans Craft, un champ peut être appliqué à n'importe quel nombre d'entries, d'users, de tags ou de globals via un "field layout" qui permet d'effectuer toutes les opérations sur les fields dans une interface drag and drop.

Les fields peuvent être groupés au sein de groupes. Ces groupes n'ont qu'une fonction organisationnelle. Créer des groupes permet de gérer plus facilement un grand nombre de champs.

#### Globals

A côté des sections et des entries, les globals peuvent être utilisées pour stocker du contenu auquel il est possible d'accéder dans vos templates: tagline, coordonnées de contact, code google analytics, etc.

Vous pouvez créer des groups de contenus en utilisant les global sets. Chaque set de globals possède son field layout et donc sa propre data structure. Les différences notables avec les sections et les entries sont que les globals ne possèdent pas d'URL et ne peuvent donc pas être visualisées comme les entries à l'aide de la fonction "live preview".

#### Users

Dans Craft, les utilisateurs servent à gérer les permissions données aux divers utilisateurs du système.

Les utilisateurs peuvent être assignés à divers groupes. Ces groupes sont utilisés pour gérer les permissions données aux utilisateurs qui en sont membres. Un utilisateurs peut être assigné à plusieurs groupes.

La data-structure des utilisateurs peut être aussi complexe que souhaitée. Via un unique Field layout, les champs souhaités peuvent être assignés à la data structure de tous vos utilisateurs.

#### Assets

Les assets sont votre gestionnaire de fichiers de Craft. Vos Assets sont enregistrés dans des Asset Sources qui correspondent à des dossiers physiques sur votre serveur.

De multiples opérations peuvent être réalisées sur vos assets et les dossiers qui les contiennent depuis la page "Assets" de votre control panel.

Comme pour les utilisateurs, un unique field layout vous permet d'assigner des custom fields à la data-structure de l'ensemble de vos Assets.

#### Tags

Les tags vous permettent de créer des folksonomies et de les appliquer à vos Entries, Users ou Assets.

Chaque tag doit être assigné à un groupe et chaque groupe de tags possède un field layout. Vous pouvez donc créer des structures de données assez complexes pour chacun de vos groupes de tags.

#### Relations

L'une des grandes forces de Craft c'est qu'il est possible très facilement de créer des relations entre Entries, Users, Assets et Tags.

Pour cela, Craft met à votre disposition des champs relationnels spécifiques:

- **Assets**: permet d'établir une relation "one to one" ou "one to many" vers des Assets
- **Entries**: permet d'établir une relation "one to one" ou "one to many" vers des Entries
- **Users**: permet d'établir une relation "one to one" ou "one to many" vers des Users
- **Tags**: permet d'établir une relation "one to one" ou "one to many" vers des Tags

Pour chacun des ces tags, vous pouvez spécifier combien d'items peuvent être liés et de quelles sources ils proviennent.

Pour exploiter ces relations dans vos templates, Craft met à votre disposition un outil extrêmement puissant: le paramètre [`relatedTo`](http://buildwithcraft.com/docs/relations#the-relatedTo-param), utilisable avec `craft.entries`, `craft.users`, `craft.assets` et `craft.tags`.

#### Routing

L'un des autres éléments intéressant de Craft c'est le routing dynamique, qui permet de séparer structure des URLs et architecture de dossiers et de fichiers.

Comme nous l'avons déjà vu, il est possible pour chaque section de spécifier la structure des URLs qu'elle contient. 

Lorsque vous souhaitez qu'un template soit référencé par une URL sans pour autant que cette URL ne correspondent à une structure physique des dossiers et fichiers, vous pouvez utiliser ce Routing Dynamique.

Il est possible créer des routes et de spécifier quel template doit être chargé par Craft. Un exemple facile à comprendre est [un template donnant accès à une archive des entries classées par année](http://buildwithcraft.com/help/entry-archive#yearly-archive-pages).

En créant une route dynamique `blog/archive/{year}` renseignant le template `blog/archive`, les URLs `blog/archive/2013` et `blog/archive/2012` vont charger le même template et rendre disponible une variable `year` utilisable par Twig et par Craft avec les paramètres [`after`](http://buildwithcraft.com/docs/templating/craft.entries#after) et [`before`](http://buildwithcraft.com/docs/templating/craft.entries#before).

#### Searching

Craft possède également un [système de recherche très puissant](http://buildwithcraft.com/docs/searching) basé sur un paramètre `search` utilisable avec les tags `craft.entries`, `craft.users`, `craft.assets` et `craft.tags`.

Pour des questions de performance, Craft fonctionne avec des Index pour ses fonctions de recherche. Il est possible d'actualiser ces Index directement depuis le Control Panel.

La construction de [formulaires de recherche dynamiques pour le front-end](http://buildwithcraft.com/docs/templating/search-form) de votre projet est également très simple. Il suffit pour cela de faire appel au tag `[craft.request]` pour [récupérer un paramètre passé en GET/POST](http://buildwithcraft.com/docs/templating/craft.request) par votre formulaire. 

## Créer vos templates

Maintenant que vous savez comment créer une structure de donnée pour votre projet dans Craft, passons à la création des pages de votre site à l'aide des templates.

Vos templates sont localisés dans le dossier `craft/templates` de votre installation

### Twig comme language de templating

Craft utilise Twig, créé par Fabien Potencier pour Symfony, comme language de templating. Twig a l'avantage de compiler les template en PHP, ce qui lui permet d'être très performant. C'est un language qui reste également assez simple d'approche, même si une période d'apprentissage existe.

Couplé à des tags, fonctions et filtres spécifiques à Craft, Twig vous permet de récupérer et de manipuler vos données au sein de vos templates.

#### Template inheritance et includes, deux concepts centraux dans Twig

Ces deux concepts sont au coeur de Twig et vont nous permettre de créer des templates efficaces et évitant au maximum les redondances inutiles. C'est le fameux principe du "Don't Repeat Yourself" (DRY).

##### Template inheritance

Un concept central à comprendre dans Twig est celui d'héritage au niveau des templates. Dans Twig on va généralement travailler avec un template "parent" qui défini le squelette de la page et différents blocks pouvant être surdéterminés par un template "enfant" qui étend ce template parent.

Les variables définies dans le template "enfant" sont accessibles dans le template parent.

Voyons voir comment cela fonctionne dans la pratique avec un exemple simple:

**Template parent: layouts/_base.html**

```
<!DOCTYPE html>
<!-- paulirish.com/2008/conditional-stylesheets-vs-css-hacks-answer-neither/ -->
<!--[if IE 7]><html class="no-js lt-ie9 lt-ie8" lang="en"><![endif]-->
<!--[if IE 8]><html class="no-js lt-ie9" lang="en"><![endif]-->
<!--[if gt IE 8]><!--><html class="no-js" lang="en"><!--<![endif]-->

<head>
	<meta charset="utf-8" />

	<title>{% if htmlTitle is defined %}{{ htmlTitle }} - Mysite{% else %}My generic title{% endif %}</title>

	<meta name="viewport" content="width=device-width, initial-scale=1" />

	<link rel="shortcut icon" href="{site_url}/favicon.ico" />
	<link rel="stylesheet" media="screen" href="{site_url}/assets/css/screen.css" />
	<link rel="stylesheet" media="print" href="{site_url}/assets/css/print.css" />

	<script src="/js/libs/modernizr.js"></script>

</head>

<body>

	{% block content %}
		<p>Dummy content overridden by child template</p>
	{% endblock %}

</body>
</html>
```

**Template enfant: news/index.html**

```
{% extends "layouts/_base.html" %}
{% set htmlTitle = "Latest News" %}

{% block content %}

	<h1>News</h1>

	{% for entry in craft.entries.section('news').find() %}
		<article>
			<h3><a href="{{ entry.url }}">{{ entry.title }}</a></h3>
			<p>Posted on {{ entry.postDate.format('F d, Y') }}</p>
			{{ entry.body.page(1) }}
			<p><a href="{{ entry.url }}">Continue reading</a></p>
		</article>
	{% endfor %}
	
{% endblock %}
```

le template news/index.html étend notre layout de base. Le contenu défini dans le block "content" du template enfant remplace celui qui est (de façon optionnelle) défini dans le template parent. La variable `htmlTitle` définie dans le template enfant est accessible dans le template parent.

Remarquez également que nous écrivons le nom du template "parent" précédé par un underscore. Craft nous permet ainsi de cacher certains templates que nous ne voulons pas voir chargé directement par les visiteurs du site.

##### Includes

Si vous avez du code qui est répétés dans beaucoup de vos templates, vous pouvez également utiliser le tag `{% include %}` qui vous permet d'inclure un template au sein d'un autre.

`{% include 'sidebars/_sidebar_default.html' %}`

#### Principaux tags dans Twig

En plus des [tags disponibles dans Twig](http://twig.sensiolabs.com/doc/tags/index.html), [Craft possède également quelques tags qui lui dont propres](http://buildwithcraft.com/docs/templating/tags). Nous reviendrons sur certains d'entre-eux dans la suite du cours.

##### Tags d'affichage, variables et propriétés

`{{ Affichage }}`: ces tags permettent d'afficher des variables. Une notation pointée permet d'accéder aux propriétés de ces variables.

Exemples:

`{{ myvariable }}`: affiche la variable "myvariable"

`{{ entry.title }}`: affiche la propriété title de la variable entry

##### Tags d'exécution

`{% Execution %}`: ces tags permettent l'exécution de tâches et sont utilisés pour créer des variables, réaliser des boucles, créer des structures de contrôle, etc.

Exemples:

Créer une variable "allentries" à laquelle est assignée un objet Craft [ElementCriteriaModel](http://buildwithcraft.com/docs/templating/elementcriteriamodel) contenant toutes les entries dans la section blog, classées par date de création en ordre descendant.

`{% set allentries = craft.entries.section('blog').limit(null).order('postDate desc').find() %}`

Boucler sur l'ensemble des entries en créant à chaque fois un objet "entry" dont nous affichons le titre.

```
{% for entry in all entries %}
	<p>{{ entry.title }}</p>
{% endfor %}
```

Créer une [structure de contôle]() vérifiant si la variable "allentries" contient au minimum une entry.

```
{% if allentries|length > 0 %}
	<p>There is at least one entry here</p>
{% endif %}
```

##### Tags de commentaires

Twig possède également un tag de commentaire: `{# Ceci est un commentaire #}`

#### Filtres

[Twig comporte de nombreux filtres](http://twig.sensiolabs.com/doc/filters/index.html) pouvant être appliqués à vos différents types de variables (string, array, number, etc). Ces filtres offrent de nombreuses possibilités et permettent à Craft de se passer de nombreux plugins pour effectuer des tâches simples. Craft possède également [ses propres filtres](http://buildwithcraft.com/docs/templating/filters). Voici quelques exemples de ce qu'il est possible d'accomplir:

Convertir une string en title case

`{{ entry.title|title }}`

Réaliser des opérations sur les dates et les formatter

`{{ entry.postDate|date_modify("+1 day")|date("m/d/Y") }}`

Vous pouvez également appliquer des filtres à plusieurs lignes de votre template et pas seulement à une variable.

```
{% filter upper %}
    This text becomes uppercase
{% endfilter %}
```

#### Fonctions

Les [fonctions disponibles dans Twig](http://twig.sensiolabs.com/doc/functions/index.html) permettent de produire et de manipuler des contenus. Craft possède également [ses propres fonctions](http://buildwithcraft.com/docs/templating/functions), en plus de celles fournies par Twig.

### Récupérer vos données à l'aide de Craft

Voyons maintenant comment récupérer vos données à l'aide des tags `craft.entries`, `craft.users`, `craft.assets` et `craft.tags` qui seront sans doute vos outils principaux.

Nous nous centrerons ici principalement sur `craft.entries`. Les autres tags ayant un fonctionnement très similaire, il vous sera facile d'appliquer les mêmes principes.

#### Entries

[`craft.entries`](http://buildwithcraft.com/docs/templating/craft.entries) est le tag que vous allez utiliser pour récupérer vos entries.

- `craft.entries.find()` vous permet de récupérer toutes les entries qui correspondent à vos critères
- `craft.entries.total()` vous permet de récupérer le total des entries correspondant à vos critères
- `craft.entries.first()` et `craft.entries.last()` vous permettent de récupérer la première ou la dernière des entries correspondant à vos critères
- `craft.entries.ids()` vous permet de récupérer la liste des ids des entries  correspondant à vos critères

##### Plusieurs façons de faire

Vous pouvez utiliser deux syntaxes dans Craft. Une syntaxe pointée ou une syntaxe passant l'ensemble des paramètres comme un seul objet.

```
{% set allEntries = craft.entries.section('news').limit(4).find() %}


{% for entry in allEntries %}

	<h2>{{ entry.title }}</h2>
	{{ entry.summary }}
	
{% endfor %}
```

```
{% set allEntries = craft.entries.find({
	section('news'),
	limit(4)
}) %}


{% for entry in allEntries %}

	<h2>{{ entry.title }}</h2>
	{{ entry.summary }}
	
{% endfor %}
```

Les deux syntaxes sont valides et chacune ont leur place. La seconde méthode est plus utile si vous devez réutiliser les paramètres plusieurs fois dans votre template.

```
{% set params = {
	section('news'),
	orderby('postDate desc')
} %}

{% set totalEntries = craft.entries.total(params) %}

Total entries: {{ totalEntries }}

{% for entry in craft.entries.find(params) %}

	<h2>{{ entry.title }}</h2>
	{{ entry.summary }}
	
{% endfor %}
```

##### Pas de résultats

Vous pouvez facilement afficher un contenu alternatif si aucun résultat n'est trouvé en [utilisant une clause {% else %} dans votre loop](http://twig.sensiolabs.org/doc/tags/for.html#the-else-clause).

```
{% set allEntries = craft.entries.section('news').limit(4).find() %}


{% for entry in allEntries %}

	<h2>{{ entry.title }}</h2>
	{{ entry.summary }}

{% else %}

	<p>no news found</p>

{% endfor %}
```

##### "Loop", "cycle" et "is divisible by"

Lorsque une boucle `{% for %}` est utilisé, il est souvent très pratique de pouvoir évaluer à quel étape de la boucle on se trouve et d'utiliser des conditionnels. Typiquement il est utile de pouvoir ouvrir et fermer une liste `<ul>` en début ou en fin de loop, de pouvoir afficher quelque chose tous les x résultats. C'est à cela que servent la variable [`loop`](http://twig.sensiolabs.org/doc/tags/for.html#the-loop-variable), la fonction [`cycle`](http://twig.sensiolabs.org/doc/functions/cycle.html) et le test [`is divisibleby`](http://twig.sensiolabs.org/doc/tests/divisibleby.html) de Twig.

Exemple: utilisation de la variable `loop`

```
{% set allEntries = craft.entries.section('news').limit(4).find() %}


{% for entry in allEntries %}
	
	{% if loop.first %}<ul>{% endif %}

	<li>
		<h2>{{ entry.title }}</h2>
		{{ entry.summary }}
	</li>

	{% if loop.last %}</ul>{% endif %}

{% endfor %}
```  

Exemple: utilisation de la fonction `cycle` pour ajouter des classes `odd` et `even`. Remarquez l'usage de `loop.index0` pour avoir une itération indexée sur zéro et non sur 1 comme avec `loop.index`.

```
{% set allEntries = craft.entries.section('news').limit(4).find() %}


{% for entry in allEntries %}
	
	{% if loop.first %}<ul>{% endif %}

	<li class="{{ cycle(['odd', 'even'], loop.index0) }}">
		<h2>{{ entry.title }}</h2>
		{{ entry.summary }}
	</li>

	{% if loop.last %}</ul>{% endif %}

{% endfor %}
```  

Exemple: utilisation du test `is divisible by` pour insérer un élément toutes les 2 itérations.

```
{% set allEntries = craft.entries.section('news').limit(4).find() %}


{% for entry in allEntries %}

	{% if loop.first %}<div class="row">{% endif %}

		<div class="item">
			<h2>{{ entry.title }}</h2>
			{{ entry.summary }}
		</div>

	{% if loop.index is divisible by(2) %}</div><div class="row">{% endif %}

	{% if loop.last %}</div>{% endif %}

{% endfor %}  
```

Les [autres tests disponibles avec Twig](http://twig.sensiolabs.org/doc/tests/index.html) valent également la peine d'être consultés, notamment le test `is defined`.

##### Pagination

Craft vous permet de [paginer vos résultats](http://buildwithcraft.com/docs/templating/tags#paginate) à l'aide du tag `paginate` et de construire une interface de pagination à l'aide des variables qui l'accompagnent.

```
{% paginate craft.entries.section('news').limit(5) as entries %}

	{# get paginated entries #}
	{% for entry in entries %}
		<article>
			<h3 class="title-item"><a href="{{ entry.url }}">{{ entry.title }}</a></h3>
			<p class="meta-info">Posted on {{ entry.postDate.format('F d, Y') }}</p>
			{{ entry.body }}
			<p><a href="{{ entry.url }}">Read More</a></p>
		</article>
	{% endfor %}
	
	{# Build pagnation interface if more than 1 page #}
	{% if paginate.totalPages > 1 %}
		<ul class="hlist pagination">
			{% if paginate.prevUrl %}
				<li><a href="{{ paginate.prevUrl }}">Previous Page</a></li>
			{% endif %}

			{% for page, url in paginate.getPrevUrls(2) %}
			    <li><a href="{{ url }}">{{ page }}</a></li>
			{% endfor %}

			<li class="current"><a href="{{ paginate.getPageUrl( paginate.currentPage ) }}">{{ paginate.currentPage }}</a></li>

			{% for page, url in paginate.getNextUrls(2) %}
			    <li><a href="{{ url }}">{{ page }}</a></li>
			{% endfor %}

			{% if paginate.nextUrl %}
				<li><a href="{{ paginate.nextUrl }}">Next Page</a></li>
			{% endif %}

		</ul>
	{% endif %}

{% endpaginate %}
```

##### Page de détail et variable "entry"

Lorsque Craft charge un template de détail et que l'URL correspond à l'URI d'une entry, le système génère une variable `entry` directement accessible dans notre template.

```
{#
 # This template gets loaded whenever a News entry’s URL is
 # requested. That’s because the News section’s Template setting is
 # set to “news/_entry”, the path to this template.
 #
 # When this template is loaded, it will already have an ‘entry’
 # variable, set to the requested News entry.
 #}

{% extends "layouts/_base.html" %}

{% block content %}

	<article>
		<h1>{{ entry.title }}</h1>
		<p>Posted on {{ entry.postDate.format('F d, Y') }}</p>
		{{ entry.body }}
	</article>

{% endblock %}
```

#### Globals

Les globals stockent du contenu qui va, comme leur nom l'indique, être disponible  globalement pour tous les templates.

Vous pouvez y accéder très facilement via leur handle de global set suivi de leur handle de global. Par exemple, pour une global appelée `tagline` dans un global set `companyInfo`:

`{{ companyInfo.tagline }}`

#### Tags

Dans Craft, on accès aux tags avec `craft.tags`, qui [possède un certain nombre de paramètres](http://buildwithcraft.com/docs/templating/craft.tags) et fonctionne dans l'ensemble comme `craft.entries` dans la mesure où il retourne un objet [ElementCriteriaModel](http://buildwithcraft.com/docs/templating/elementcriteriamodel).

Deux articles sur buildwithcraft.com vous montrent comment obtenir une [liste de tous les tags utilisés par les entries d'une section](http://buildwithcraft.com/help/active-tags), ou encore comment créer, à l'aide d'une route dynamique, [une page d'archive reprenant toutes les entries liées à un tag](http://buildwithcraft.com/help/tag-urls). 

#### Users

Le tag `craft.users` permet d'accéder aux utilisateurs de votre site. Ce tag possède lui aussi [un certain nombre de paramètres, dont certains lui sont propres](http://buildwithcraft.com/docs/templating/craft.users). Son fonctionnement est semblable au tag `craft.entries` dans la mesure où il retourne un objet [ElementCriteriaModel](http://buildwithcraft.com/docs/templating/elementcriteriamodel).

#### Assets et transformations

Le tag `craft.assets` permet d'accéder aux Assets de votre site. Ce tag possède lui aussi [un certain nombre de paramètres, dont certains lui sont propres](http://buildwithcraft.com/docs/templating/craft.assets). Son fonctionnement est semblable au tag `craft.entries` dans la mesure où il retourne un objet [ElementCriteriaModel](http://buildwithcraft.com/docs/templating/elementcriteriamodel).

Si vos assets sont des images, Craft vous permet d'effectuer des transformations de celles-ci, soit à l'upload (via votre control panel: Settings, Assets, Image Transforms), soit dynamiquement dans vos templates.

Si vous définissez une transformation directement dans le control panel et que vous lui donnez comme hangle `thumb` vous pouvez y accéder dans vos template de la façon suivante:

`<img src="{{ asset.getUrl('thumb') }}" width="{{ asset.getWidth('thumb') }}" height="{{ asset.getHeight('thumb') }}" />`

Vous pouvez également définir dynamiquement une transformation dans vos templates

```
{% set transform = {
    width: 100,
    height: 100,
    mode: 'crop',
    position: 'top-center'
} %}

<img src="{{ asset.getUrl(transform) }}" width="{{ asset.getWidth(transform) }}" height="{{ asset.getHeight(transform) }}" />
```

## Aller plus loin

### Configuration pour environnements multiples

Craft fourni nativement une façon simple de gérer des environnements multiples (local, dev, online) via l'urlisation de différents Arrays dans les fichiers general.php et db.php inclus dans le dossier config/.



### Matrix

## Ressources
