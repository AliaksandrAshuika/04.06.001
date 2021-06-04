### Premiers pas

Dans cet ensemble d'articles, vous découvrirez les **principes** de base de Nest. Pour nous familiariser avec les éléments constitutifs essentiels des applications Nest, nous allons créer une application CRUD de base avec des fonctionnalités qui couvrent beaucoup de terrain à un niveau d'introduction.

#### Langue

Nous sommes amoureux de [TypeScript](https://www.typescriptlang.org/) , mais surtout - nous aimons [Node.js](https://nodejs.org/en/) . C'est pourquoi Nest est compatible avec TypeScript et **JavaScript pur** . Nest tire parti des dernières fonctionnalités du langage, donc pour l'utiliser avec JavaScript vanille, nous avons besoin d'un compilateur [Babel.](https://babeljs.io/)

Nous utiliserons principalement TypeScript dans les exemples que nous fournissons, mais vous pouvez toujours **basculer les extraits de code** vers la syntaxe JavaScript vanille (cliquez simplement pour basculer le bouton de langue dans le coin supérieur droit de chaque extrait).

#### Conditions préalables

Veuillez vous assurer que [Node.js](https://nodejs.org/) (&gt;= 10.13.0) est installé sur votre système d'exploitation.

#### Installer

La configuration d'un nouveau projet est assez simple avec l' [interface de ligne de commande Nest](/cli/overview) . Avec [npm](https://www.npmjs.com/) installé, vous pouvez créer un nouveau projet Nest avec les commandes suivantes dans votre terminal OS :

```bash
$ npm i -g @nestjs/cli
$ nest new project-name
```

Le `project` sera créé, les modules de nœud et quelques autres fichiers passe-partout seront installés et un `src/` sera créé et rempli de plusieurs fichiers principaux.

<div class="file-tree">
  <div class="item">src</div>
  <div class="children">
    <div class="item">app.controller.ts</div>
    <div class="item">app.controller.spec.ts</div>
    <div class="item">app.module.ts</div>
    <div class="item">app.service.ts</div>
    <div class="item">main.ts</div>
  </div>
</div>

Voici un bref aperçu de ces fichiers principaux :

|                          |                                                                                                                                   |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| `app.controller.ts`      | Un contrôleur de base avec une seule route.                                                                                       |
| `app.controller.spec.ts` | L'unité teste le contrôleur.                                                                                                      |
| `app.module.ts`          | Le module racine de l'application.                                                                                                |
| `app.service.ts`         | Un service de base avec une seule méthode.                                                                                        |
| `main.ts`                | Le fichier d'entrée de l'application qui utilise la fonction principale `NestFactory` pour créer une instance d'application Nest. |

Le `main.ts` inclut une fonction asynchrone, qui **amorcera** notre application :

```typescript
@@filename(main)

import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}
bootstrap();
@@switch
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}
bootstrap();
```

Pour créer une instance d'application Nest, nous utilisons la classe `NestFactory` `NestFactory` expose quelques méthodes statiques qui permettent de créer une instance d'application. La `create()` renvoie un objet d'application, qui remplit l'interface `INestApplication` Cet objet fournit un ensemble de méthodes qui sont décrites dans les prochains chapitres. Dans l' `main.ts` ci-dessus, nous démarrons simplement notre écouteur HTTP, qui permet à l'application d'attendre les requêtes HTTP entrantes.

Notez qu'un projet échafaudé avec la Nest CLI crée une structure de projet initiale qui encourage les développeurs à suivre la convention de conserver chaque module dans son propre répertoire dédié.

<app-banner-courses></app-banner-courses>

#### Plate-forme

Nest vise à être un framework indépendant de la plate-forme. L'indépendance de la plate-forme permet de créer des éléments logiques réutilisables dont les développeurs peuvent tirer parti dans plusieurs types d'applications différents. Techniquement, Nest est capable de fonctionner avec n'importe quel framework HTTP Node une fois qu'un adaptateur est créé. Il existe deux plates-formes HTTP prises en charge par [défaut](https://www.fastify.io)[ : express](https://expressjs.com/) et fastify . Vous pouvez choisir celui qui convient le mieux à vos besoins.

|                    |                                                                                                                                                                                                                                                                                                                                                                                                         |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `platform-express` | [Express](https://expressjs.com/) est un framework web minimaliste bien connu pour node. Il s'agit d'une bibliothèque prête pour la production, testée au combat, avec de nombreuses ressources mises en œuvre par la communauté. Le `@nestjs/platform-express` est utilisé par défaut. De nombreux utilisateurs sont bien servis avec Express et n'ont besoin de prendre aucune mesure pour l'activer. |
| `platform-fastify` | [Fastify est un framework à](https://www.fastify.io/) hautes performances et à faible surcharge hautement axé sur une efficacité et une vitesse maximales. Lisez comment l'utiliser [ici](/techniques/performance) .                                                                                                                                                                                    |

Quelle que soit la plate-forme utilisée, elle expose sa propre interface d'application. Ceux-ci sont considérés respectivement comme `NestExpressApplication` et `NestFastifyApplication` .

Lorsque vous transmettez un type à la `NestFactory.create()` , comme dans l'exemple ci-dessous, l' `app` aura des méthodes disponibles exclusivement pour cette plate-forme spécifique. Notez, cependant, que vous n'avez pas **besoin** de spécifier un type à **moins que** vous ne souhaitiez réellement accéder à l'API de la plate-forme sous-jacente.

```typescript
const app = await NestFactory.create<NestExpressApplication>(AppModule);
```

#### Exécuter l'application

Une fois le processus d'installation terminé, vous pouvez exécuter la commande suivante à l'invite de commande de votre système d'exploitation pour démarrer l'application à l'écoute des requêtes HTTP entrantes :

```bash
$ npm run start
```

Cette commande démarre l'application avec le serveur HTTP à l'écoute sur le port défini dans le fichier `src/main.ts` Une fois l'application en cours d'exécution, ouvrez votre navigateur et accédez à `http://localhost:3000/` . Vous devriez voir le `Hello World!` un message.
