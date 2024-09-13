---
title: Dessiner XForm sur la page
linktitle: Dessiner XForm sur la page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à dessiner des XForms au format PDF à l'aide d'Aspose.PDF pour .NET avec ce guide complet étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-operators/draw-xform-on-page/
---
## Introduction

Créer des documents PDF dynamiques et visuellement attrayants est devenu une compétence essentielle dans le monde numérique d'aujourd'hui. Que vous soyez un développeur travaillant sur la génération de documents ou un concepteur axé sur l'esthétique, comprendre comment manipuler les PDF est inestimable. Dans ce didacticiel, nous allons découvrir comment dessiner un XForm sur une page à l'aide de la bibliothèque Aspose.PDF pour .NET. Ce guide étape par étape vous guidera dans la création de XForms et leur placement efficace sur vos pages PDF.

## Prérequis

Avant de commencer, vous aurez besoin de quelques éléments pour garantir une expérience fluide :

1.  Bibliothèque Aspose.PDF pour .NET : assurez-vous que la bibliothèque Aspose.PDF est installée. Si vous ne l'avez pas encore installée, téléchargez-la à partir de[ici](https://releases.aspose.com/pdf/net/).
2. Environnement de développement : un environnement de développement .NET fonctionnel (tel que Visual Studio 2019 ou version ultérieure).
3. Exemples de fichiers PDF et d'images : vous aurez besoin d'un fichier PDF de base dans lequel nous dessinerons le XForm et d'une image pour démontrer la fonctionnalité. N'hésitez pas à utiliser l'exemple de fichier PDF et une image disponibles dans votre répertoire de documents.

## Paquets d'importation

Une fois les prérequis définis, vous devez importer les espaces de noms nécessaires dans votre projet .NET. Cela vous permettra d'accéder aux classes et méthodes fournies par Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
```

Ces espaces de noms fournissent les composants essentiels nécessaires pour manipuler des documents PDF et utiliser les fonctionnalités de dessin.

Décomposons le processus en étapes faciles à comprendre. Chaque étape comprend des instructions claires pour vous aider à comprendre et à appliquer les concepts de manière efficace.

## Étape 1 : Initialiser le document et définir les chemins

Comprendre les bases

Dans cette étape, nous allons configurer notre document et définir les chemins d’accès aux fichiers pour le PDF d’entrée, le PDF de sortie et le fichier image qui sera utilisé dans le XForm.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // remplacer par votre chemin
string imageFile = dataDir + "aspose-logo.jpg"; // L'image à dessiner
string inFile = dataDir + "DrawXFormOnPage.pdf"; // Fichier PDF d'entrée
string outFile = dataDir + "blank-sample2_out.pdf"; // Fichier PDF de sortie
```

 Ici,`dataDir`est le répertoire de base où se trouvent vos fichiers, assurez-vous donc de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel.

## Étape 2 : Créer une nouvelle instance de document

Chargement du document PDF

Ensuite, nous allons créer une instance de la classe Document qui représente notre PDF d’entrée.

```csharp
using (Document doc = new Document(inFile))
{
    // D'autres étapes suivront ici...
}
```

 En utilisant le`using` L'instruction garantit que les ressources sont automatiquement nettoyées une fois les opérations terminées.

## Étape 3 : Accédez au contenu de la page et commencez à dessiner

Configuration des opérations de dessin

Nous allons maintenant accéder au contenu de la première page de notre document. C'est ici que nous allons insérer nos commandes de dessin.

```csharp
OperatorCollection pageContents = doc.Pages[1].Contents;
```

Cela nous donne le contrôle sur le contenu de la page, nous permettant d'insérer des opérateurs graphiques pour dessiner notre XForm.

## Étape 4 : Enregistrer et restaurer l’état graphique

Préserver l'état graphique

Avant de dessiner le XForm, il est essentiel de sauvegarder l'état graphique actuel. Cela permet de maintenir le contexte de rendu.

```csharp
pageContents.Insert(1, new GSave());
pageContents.Add(new GRestore());
pageContents.Add(new GSave());
```

 Le`GSave` L'opérateur enregistre l'état graphique actuel, tandis que`GRestore`le restaure plus tard, garantissant que nous revenons à notre contexte d'origine après le dessin.

## Étape 5 : Créer le XForm

Créer votre XForm

Ici, nous allons créer notre objet XForm. Il s'agit du conteneur de nos opérations de dessin, nous permettant de les encapsuler proprement.

```csharp
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
```

 Cette ligne crée un nouveau XForm et l'ajoute aux formulaires de ressources de la page.`GSave` est à nouveau utilisé pour préserver l'état graphique dans le XForm.

## Étape 6 : ajouter une image et définir les dimensions

Intégration de l'imagerie

Ensuite, nous allons charger une image dans notre XForm et définir sa taille.

```csharp
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
Stream imageStream = new FileStream(imageFile, FileMode.Open);
form.Resources.Images.Add(imageStream);
```

 Ce code définit la taille de l'image avec`ConcatenateMatrix`, qui définit comment l'image sera transformée. Le flux d'images est ajouté aux ressources du XForm.

## Étape 7 : Dessinez l'image

Affichage de l'image

 Maintenant, utilisons le`Do` opérateur pour dessiner réellement l'image que nous avons ajoutée au XForm sur notre page.

```csharp
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());
```

 Le`Do` L'opérateur est le moyen par lequel nous rendons l'image sur la page PDF. Après cela, nous restaurons l'état graphique.

## Étape 8 : Positionnez le XForm sur la page

Placer le XForm

 Pour restituer le XForm à des coordonnées spécifiques sur la page, nous utiliserons un autre`ConcatenateMatrix` opération.

```csharp
pageContents.Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
pageContents.Add(new Do(form.Name));
pageContents.Add(new GRestore());
```

 Cet extrait place le XForm aux coordonnées`x=100`, `y=500`.

## Étape 9 : Dessinez-le à nouveau à un autre endroit

Réutiliser le XForm

Exploitons le même XForm et dessinons-le à une position différente sur la page.

```csharp
pageContents.Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
pageContents.Add(new Do(form.Name));
pageContents.Add(new GRestore());
```

Cela vous permet de réutiliser le même XForm, maximisant ainsi l'efficacité de la mise en page de votre document.

## Étape 10 : Finaliser et enregistrer le document

Sauvegarder votre travail

Enfin, nous devons enregistrer les modifications que nous avons apportées à notre document PDF.

```csharp
doc.Save(outFile);
```

Cette ligne écrit votre document modifié dans le chemin de fichier de sortie spécifié.

## Conclusion

Félicitations ! Vous avez appris avec succès à dessiner un XForm sur une page PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant ces étapes, vous êtes désormais équipé pour améliorer vos PDF avec des formulaires dynamiques et des éléments visuels. Que vous prépariez des rapports, des supports marketing ou des documents électroniques, l'intégration de XForms d'image peut enrichir considérablement le contenu. Alors, soyez créatif et commencez à explorer davantage de fonctionnalités avec Aspose.PDF !

## FAQ

### Qu'est-ce qu'un XForm dans Aspose.PDF ?
Un XForm est un formulaire réutilisable qui peut encapsuler des graphiques et du contenu, ce qui permet de les dessiner sur plusieurs pages ou à différents emplacements dans un document PDF.

### Comment modifier la taille de l'image dans XForm ?
 Vous pouvez ajuster la taille en modifiant les paramètres dans le`ConcatenateMatrix` opérateur qui définit la mise à l'échelle du contenu dessiné.

### Puis-je ajouter du texte avec des images dans un XForm ?
Oui ! Vous pouvez également ajouter du texte à l'aide des opérateurs de texte fournis par la bibliothèque Aspose.PDF, en suivant une approche similaire à celle de l'ajout d'images.

### L'utilisation d'Aspose.PDF est-elle gratuite ?
 Bien qu'Aspose.PDF propose une version d'essai gratuite, une licence est nécessaire pour une utilisation continue au-delà de la période d'essai. Vous pouvez explorer les options de licence[ici](https://purchase.aspose.com/buy).

### Où puis-je trouver une documentation plus détaillée ?
 Vous pouvez retrouver la documentation complète d'Aspose.PDF[ici](https://reference.aspose.com/pdf/net/).