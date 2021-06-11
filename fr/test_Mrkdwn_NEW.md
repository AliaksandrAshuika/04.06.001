# Fichiers de démarques

![1](https://prikolnye-kartinki.ru/img/picture/Jan/31/cd47b809864a288682ad43078a9642ab/1.jpg)

Vous pouvez écrire du contenu dans des fichiers Markdown standard (par exemple, des fichiers se terminant par `.md` ). Jupyter Book prend en charge toute syntaxe Markdown prise en charge par les blocs-notes Jupyter. Jupyter Notebook Markdown est une extension d'une version de Markdown appelée [CommonMark Markdown](https://commonmark.org/) . Il contient de nombreux éléments pour le traitement de texte standard, bien qu'il manque de nombreuses fonctionnalités utilisées pour la publication et la documentation.

```{note}
If you'd like a more in-depth overview and guide to CommonMark Markdown, see
[the CommonMark Markdown tutorial](https://commonmark.org/help/tutorial/).
```

Cette page décrit certaines fonctionnalités de base de Jupyter Notebook Markdown et explique comment les inclure dans votre livre.

```{margin}
Jupyter Book also supports a fancier version of Markdown called **MyST Markdown**. This
is a slightly extended flavour of Jupyter Notebook Markdown. It
allows you to include citations and cross-references, and control more complex
functionality like adding content to the margin. For more
information, check out {doc}`../content/myst`.
```

## Intégration des médias

### Ajout d'images

Vous pouvez référencer des supports externes tels que des images de votre fichier Markdown. Si vous utilisez des chemins relatifs, ils continueront de fonctionner lorsque les fichiers Markdown seront copiés, tant qu'ils pointent vers un fichier qui se trouve à l'intérieur du référentiel.

Voici une image relative à la racine du contenu du livre

![C-3PO_droid](https://jupyterbook.org/_images/C-3PO_droid.png)

Il a été généré avec ce code :

```md
![C-3PO_droid](../images/C-3PO_droid.png)
```

:::{voir également}[](../content/figures.md) pour plus d'informations. :::

### Ajout de films

Vous pouvez même intégrer des références à des films sur le Web ! Par exemple, voici un petit GIF pour vous !

![giphy](https://media.giphy.com/media/yoJC2A59OCZHs1LXvW/giphy.gif)

Cela sera inclus dans votre livre quand il sera construit.

## Mathématiques

Pour les sorties HTML, Jupyter Book utilise l'excellente [bibliothèque MathJax](http://docs.mathjax.org/en/latest/) , ainsi que la configuration par défaut de Jupyter Notebook, pour le rendu des mathématiques à partir de la syntaxe de style LaTeX.

Par exemple, voici une expression mathématique rendue avec MathJax :

$$ P(A_1 \cup A_2 \cup A_3) &amp; = P(B \cup A_3) \ &amp; = P(B) + P(A_3) - P(BA_3) \ &amp;= P(A_1) + P(A_2) - P(A_1A_2) + P(A_3) - P(A_1A_3 \cup A_2A_3) \ &amp;= \sum_{i=1}^3 P(A_i) - \mathop{\sum \sum}_{1 \le i &lt; j \le 3} P(A_iA_j) + P(A_1A_2A_3) $$

:::{voir également}[](../content/math.md) pour plus d'informations. :::

### Mathématiques au niveau des blocs

Vous pouvez inclure des mathématiques au niveau des blocs en enveloppant vos formules dans des caractères `$$` Par exemple, le bloc suivant :

```md
$$
wow = its^{math}
$$
```

Résultats dans cette sortie :

$$ wow = son^{math} $$

Vous pouvez également inclure des blocs mathématiques en utilisant la syntaxe de style LaTeX en utilisant `\begin{align*}` . Par exemple, le bloc suivant :

```latex
\begin{align*}
yep = its_{more}^{math}
\end{align*}
```

Résulte en:

\begin{align*} oui = its_{more}^{math} \end{align*}

:::{important} Cela nécessite l' [`amsmath` extension](math:latex) amsmath MyST . :::

## Markdown étendu avec MyST Markdown

En plus de CommonMark Markdown, Jupyter Book prend également en charge une version plus complète de Markdown appelée **MyST Markdown** . Il s'agit d'un sur-ensemble de CommonMark qui comprend des éléments syntaxiques utiles pour la publication de récits informatiques. Pour plus d'informations sur MyST Markdown, consultez[](../content/myst.md) .
