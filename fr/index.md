---
layout: Publier
title: Web Vitals
description: Des métriques essentielles pour un site sain
hero: image/admin/BHaoqqR73jDWe6FL2kfw.png
authors:
  - philipwalton
date: '2020-04-30'
updated: '2020-07-21'
tags:
  - métrique
  - performance
  - web-vitaux
---

L'optimisation de la qualité de l'expérience utilisateur est la clé du succès à long terme de tout site sur le Web. Que vous soyez propriétaire d'une entreprise, spécialiste du marketing ou développeur, Web Vitals peut vous aider à quantifier l'expérience de votre site et à identifier les opportunités d'amélioration.

## Aperçu

Web Vitals est une initiative de Google visant à fournir des conseils unifiés pour les signaux de qualité qui sont essentiels pour offrir une excellente expérience utilisateur sur le Web.

Google a fourni un certain nombre d'outils au fil des ans pour mesurer et rendre compte des performances. Certains développeurs sont des experts dans l'utilisation de ces outils, tandis que d'autres ont trouvé l'abondance d'outils et de métriques difficile à suivre.

Les propriétaires de sites ne devraient pas avoir à être des gourous de la performance pour comprendre la qualité de l'expérience qu'ils offrent à leurs utilisateurs. L'initiative Web Vitals vise à simplifier le paysage et à aider les sites à se concentrer sur les métriques les plus importantes, les **Core Web Vitals** .

## Éléments essentiels du Web

Les Web Vitals de base sont le sous-ensemble des Web Vitals qui s'appliquent à toutes les pages Web, doivent être mesurés par tous les propriétaires de sites et seront affichés dans tous les outils Google. Chacun des Core Web Vitals représente une facette distincte de l'expérience utilisateur, est mesurable [sur le terrain](/user-centric-performance-metrics/#how-metrics-are-measured) et reflète l'expérience réelle d'un résultat critique [centré sur l'utilisateur](/user-centric-performance-metrics/#how-metrics-are-measured) .

Les métriques qui composent Core Web Vitals [évolueront au](#evolving-web-vitals) fil du temps. L'ensemble actuel pour 2020 se concentre sur trois aspects de l'expérience utilisateur - *chargement* , *interactivité* et *stabilité visuelle* - et comprend les métriques suivantes (et leurs seuils respectifs) :

<div class="w-stack w-stack--center w-stack--md">{% Img src="image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ZZU8Z7TMKXmzZT2mCjJU.svg", alt="Recommandations de seuil de peinture la plus riche en contenu", width="400", height="350" %} {% Img src="image/tcFciH4Qr1GuF3MyByBr2", height="350" %} {% XGL. svg", alt="Recommandations de seuil de délai de première entrée", width="400", height="350" %} {% Img src="image/tcFciHGuF3MxnTr1y5ue01OGLBn2/dgpDFckbHwwOKdIGDa3N.svg", alt="Recommandations de seuil de décalage de mise en page cumulatif" , largeur="400", hauteur="350" %}</div>

- **[Largest Contentful Paint (LCP)](/lcp/)** : mesure *les* performances de chargement. Pour offrir une bonne expérience utilisateur, le LCP doit se produire dans les **2,5 secondes suivant** le début du chargement de la page.
- **[First Input Delay (FID)](/fid/)** : mesure l' *interactivité* . Pour offrir une bonne expérience utilisateur, les pages doivent avoir un FID de **100 millisecondes** ou moins.
- **[Cumulative Layout Shift (CLS)](/cls/)** : mesure *la stabilité visuelle* . Pour offrir une bonne expérience utilisateur, les pages doivent maintenir un CLS de **0,1.** ou moins.

Pour chacune des métriques ci-dessus, afin de vous assurer que vous atteignez la cible recommandée pour la plupart de vos utilisateurs, un bon seuil à mesurer est le **75e centile** des chargements de pages, segmenté sur les appareils mobiles et de bureau.

Les outils qui évaluent la conformité de Core Web Vitals doivent considérer qu'une page passe si elle atteint les objectifs recommandés au 75e centile pour l'ensemble des trois mesures ci-dessus.

{% Aside %} Pour en savoir plus sur la recherche et la méthodologie qui sous-tendent ces recommandations, consultez : [Définir les seuils des métriques Core Web Vitals](/defining-core-web-vitals-thresholds/) {% endAside %}

### Outils pour mesurer et rapporter les Core Web Vitals

Google pense que les Core Web Vitals sont essentiels à toutes les expériences Web. En conséquence, il s'engage à faire apparaître ces métriques [dans tous ses outils populaires](/vitals-tools/) . Les sections suivantes détaillent les outils qui prennent en charge Core Web Vitals.

#### Outils de terrain pour mesurer Core Web Vitals

Le[rapport sur l'expérience utilisateur Chrome](https://developers.google.com/web/tools/chrome-user-experience-report) collecte des données de mesure d'utilisateur réelles et anonymes pour chaque Core Web Vital. Ces données permettent aux propriétaires de sites d'évaluer rapidement leurs performances sans les obliger à instrumenter manuellement des analyses sur leurs pages, et alimentent des outils tels que [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) et le rapport [Core Web Vitals de la](https://support.google.com/webmasters/answer/9205520) Search Console.

<div class="w-table-wrapper">
  <table>
    <tr>
      <td> </td>
      <td>LCP</td>
      <td>FID</td>
      <td>CLS</td>
    </tr>
    <tr>
      <td><a href="https://developers.google.com/web/tools/chrome-user-experience-report">Rapport sur l'expérience utilisateur Chrome</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr>
      <td><a href="https://developers.google.com/speed/pagespeed/insights/">Aperçu de la vitesse de page</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr>
      <td><a href="https://support.google.com/webmasters/answer/9205520">Search Console (rapport Core Web Vitals)</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
  </table>
</div>

{% Aside %} Pour obtenir des conseils sur l'utilisation de ces outils et sur l'outil qui convient le mieux à votre cas d'utilisation, consultez : [Premiers pas avec la mesure de Web Vitals](/vitals-measurement-getting-started/) {% endAside %}

Les données fournies par le rapport d'expérience utilisateur Chrome offrent un moyen rapide d'évaluer les performances des sites, mais elles ne fournissent pas la télémétrie détaillée par page vue qui est souvent nécessaire pour diagnostiquer, surveiller et réagir rapidement aux régressions avec précision. Par conséquent, nous recommandons fortement aux sites de mettre en place leur propre surveillance des utilisateurs réels.

#### Mesurer les éléments essentiels du Web en JavaScript

Chacun des Core Web Vitals peut être mesuré en JavaScript à l'aide d'API Web standard.

Le moyen le plus simple de mesurer tous les Core Web Vitals est d'utiliser la [bibliothèque JavaScript web-vitals](https://github.com/GoogleChrome/web-vitals) , un petit wrapper prêt pour la production autour des API Web sous-jacentes qui mesure chaque métrique d'une manière qui correspond avec précision à la façon dont elles sont rapportées par tous les Outils Google répertoriés ci-dessus.

Avec la [bibliothèque web-vitals](https://github.com/GoogleChrome/web-vitals) , mesurer chaque métrique est aussi simple que d'appeler une seule fonction (voir la documentation pour l' [utilisation](https://github.com/GoogleChrome/web-vitals#usage) complète et les détails de l' [API) :](https://github.com/GoogleChrome/web-vitals#api)

```js
import {getCLS, getFID, getLCP} from 'web-vitals';

function sendToAnalytics(metric) {
  const body = JSON.stringify(metric);
  // Use `navigator.sendBeacon()` if available, falling back to `fetch()`.
  (navigator.sendBeacon && navigator.sendBeacon('/analytics', body)) ||
      fetch('/analytics', {body, method: 'POST', keepalive: true});
}

getCLS(sendToAnalytics);
getFID(sendToAnalytics);
getLCP(sendToAnalytics);
```

Une fois que vous avez configuré votre site pour utiliser la [bibliothèque web-vitals](https://github.com/GoogleChrome/web-vitals) pour mesurer et envoyer vos données Core Web Vitals à un point de terminaison d'analyse, l'étape suivante consiste à agréger et à générer des rapports sur ces données pour voir si vos pages atteignent les seuils recommandés pour au moins 75 % des visites de pages.

Bien que certains fournisseurs d'analyses prennent en charge les métriques Core Web Vitals, même ceux qui ne le font pas devraient inclure des fonctionnalités de métrique personnalisées de base qui vous permettent de mesurer les Core Web Vitals dans leur outil.

Un exemple de ceci est le rapport [Web Vitals](https://github.com/GoogleChromeLabs/web-vitals-report) , qui permet aux propriétaires de sites de mesurer leurs Core Web Vitals à l'aide de Google Analytics. Pour obtenir des conseils sur la mesure de Core Web Vitals à l'aide d'autres outils d'analyse, consultez [Bonnes pratiques pour mesurer les Web Vitals sur le terrain](/vitals-field-measurement-best-practices/) .

Vous pouvez également créer des rapports sur chacun des principaux Web Vitals sans écrire de code à l'aide de l' [extension Web Vitals Chrome](https://github.com/GoogleChrome/web-vitals-extension) . Cette extension utilise la [bibliothèque web-vitals](https://github.com/GoogleChrome/web-vitals) pour mesurer chacune de ces métriques et les afficher aux utilisateurs lorsqu'ils naviguent sur le Web.

Cette extension peut être utile pour comprendre les performances de vos propres sites, des sites de vos concurrents et du Web en général.

<div class="w-table-wrapper">
  <table>
    <thead>
      <tr>
        <th> </th>
        <th>LCP</th>
        <th>FID</th>
        <th>CLS</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><a href="https://github.com/GoogleChrome/web-vitals">web-vitaux</a></td>
        <td>✔</td>
        <td>✔</td>
        <td>✔</td>
      </tr>
      <tr>
        <td><a href="https://github.com/GoogleChrome/web-vitals-extension">Extension Web Vitals</a></td>
        <td>✔</td>
        <td>✔</td>
        <td>✔</td>
      </tr>
    </tbody>
  </table>
</div>

Alternativement, les développeurs qui préfèrent mesurer ces métriques directement via les API Web sous-jacentes peuvent se référer à ces guides de métriques pour plus de détails sur la mise en œuvre :

- [Mesurer le LCP en JavaScript](/lcp/#measure-lcp-in-javascript)
- [Mesurer le FID en JavaScript](/fid/#measure-fid-in-javascript)
- [Mesurer CLS en JavaScript](/cls/#measure-cls-in-javascript)

{% Aside %} Pour obtenir des conseils supplémentaires sur la façon de mesurer ces métriques à l'aide de services d'analyse populaires (ou de vos propres outils d'analyse internes), consultez : [Meilleures pratiques pour mesurer les Web Vitals sur le terrain](/vitals-field-measurement-best-practices/) {% endAside %}

#### Outils de laboratoire pour mesurer Core Web Vitals

Bien que tous les Core Web Vitals soient avant tout des mesures de terrain, beaucoup d'entre eux sont également mesurables en laboratoire.

La mesure en laboratoire est le meilleur moyen de tester les performances des fonctionnalités pendant le développement, avant qu'elles ne soient mises à la disposition des utilisateurs. C'est également le meilleur moyen de détecter les régressions de performances avant qu'elles ne se produisent.

Les outils suivants peuvent être utilisés pour mesurer les Core Web Vitals dans un environnement de laboratoire :

<div class="w-table-wrapper">
  <table>
    <thead>
      <tr>
        <th> </th>
        <th>LCP</th>
        <th>FID</th>
        <th>CLS</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><a href="https://developers.google.com/web/tools/chrome-devtools">Outils de développement Chrome</a></td>
        <td>✔</td>
        <td>(utiliser le <a href="/tbt/">TBT à la</a> place)</td>
        <td>✔</td>
      </tr>
      <tr>
        <td><a href="https://developers.google.com/web/tools/lighthouse">Phare</a></td>
        <td>✔</td>
        <td>(utiliser le <a href="/tbt/">TBT à la</a> place)</td>
        <td>✔</td>
      </tr>
    </tbody>
  </table>
</div>

{% De côté %} Des outils comme Lighthouse qui chargent des pages dans un environnement simulé sans utilisateur ne peuvent pas mesurer le FID (il n'y a pas d'entrée utilisateur). Cependant, la métrique du temps de blocage total (TBT) est mesurable en laboratoire et constitue un excellent proxy pour le FID. Les optimisations de performances qui améliorent le TBT en laboratoire devraient améliorer le FID sur le terrain (voir les recommandations de performances ci-dessous). {% endAside %}

Bien que les mesures en laboratoire soient un élément essentiel pour offrir de grandes expériences, elles ne remplacent pas les mesures sur le terrain.

Les performances d'un site peuvent varier considérablement en fonction des capacités de l'appareil d'un utilisateur, des conditions de son réseau, des autres processus pouvant être exécutés sur l'appareil et de la manière dont ils interagissent avec la page. En fait, chacune des métriques Core Web Vitals peut avoir son score affecté par l'interaction de l'utilisateur. Seule la mesure sur le terrain peut capturer avec précision l'image complète.

### Recommandations pour améliorer vos scores

Une fois que vous avez mesuré les Core Web Vitals et identifié les domaines à améliorer, l'étape suivante consiste à optimiser. Les guides suivants proposent des recommandations spécifiques sur la façon d'optimiser vos pages pour chacun des éléments essentiels du Web :

- [Optimiser le LCP](/optimize-lcp/)
- [Optimiser le FID](/optimize-fid/)
- [Optimiser CLS](/optimize-cls/)

## Autres Web Vitals

Alors que les Core Web Vitals sont les métriques essentielles pour comprendre et offrir une excellente expérience utilisateur, il existe également d'autres métriques vitales.

Ces autres Web Vitals servent souvent de proxy ou de métriques supplémentaires pour les Core Web Vitals, pour aider à capturer une plus grande partie de l'expérience ou pour aider à diagnostiquer un problème spécifique.

Par exemple, les métriques [Time to First Byte (TTFB)](/time-to-first-byte/) et [First Contentful Paint (FCP)](/fcp/) sont tous deux des aspects essentiels de l' *expérience de chargement* et sont tous deux utiles pour diagnostiquer les problèmes avec LCP (temps de [réponse du serveur](/overloaded-server/) lents ou [ressources bloquant le rendu](/render-blocking-resources/) , respectivement) .

De même, des mesures telles que le [temps de blocage total (TBT)](/tbt/) et le [temps d'interaction (TTI)](/tti/) sont des mesures de laboratoire essentielles pour détecter et diagnostiquer les *problèmes d'interactivité* potentiels qui auront un impact sur le FID. Cependant, ils ne font pas partie de l'ensemble Core Web Vitals, car ils ne sont pas mesurables sur le terrain et ne reflètent pas un résultat [centré sur l'utilisateur.](/user-centric-performance-metrics/#how-metrics-are-measured)

## Web Vitals en évolution

Web Vitals et Core Web Vitals représentent les meilleurs signaux disponibles aujourd'hui aux développeurs pour mesurer la qualité de l'expérience sur le Web, mais ces signaux ne sont pas parfaits et des améliorations ou des ajouts futurs doivent être attendus.

Les **Core Web Vitals** sont pertinents pour toutes les pages Web et présentés dans les outils Google pertinents. Les modifications apportées à ces mesures auront un impact de grande envergure ; en tant que tels, les développeurs doivent s'attendre à ce que les définitions et les seuils des Core Web Vitals soient stables et que les mises à jour soient notifiées au préalable et à une cadence annuelle prévisible.

Les autres Web Vitals sont souvent spécifiques au contexte ou à l'outil, et peuvent être plus expérimentaux que les Core Web Vitals. En tant que tels, leurs définitions et seuils peuvent changer avec une plus grande fréquence.

Pour tous les Web Vitals, les changements seront clairement documentés dans ce [CHANGELOG](http://bit.ly/chrome-speed-metrics-changelog) public.
