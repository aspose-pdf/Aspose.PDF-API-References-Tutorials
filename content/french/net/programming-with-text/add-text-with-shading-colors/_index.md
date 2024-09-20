---
title: Ajouter du texte avec des couleurs d'ombrage dans un fichier PDF
linktitle: Ajouter du texte avec des couleurs d'ombrage dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter un ombrage de texte dans des fichiers PDF à l'aide d'Aspose.PDF pour .NET grâce à ce didacticiel étape par étape. Personnalisez vos documents avec des dégradés de couleurs.
type: docs
weight: 80
url: /fr/net/programming-with-text/add-text-with-shading-colors/
---
## Introduction

Avez-vous déjà ressenti le besoin de faire ressortir visuellement des documents PDF avec un peu de couleur ? Peut-être avez-vous travaillé avec des PDF et pensé : « Il faut quelque chose de plus pour les faire ressortir. » Eh bien, ne cherchez plus ! Avec Aspose.PDF pour .NET, vous pouvez facilement ajouter du texte avec des couleurs d'ombrage à vos fichiers PDF. Que vous prépariez un document pour une présentation ou que vous souhaitiez simplement faire briller une partie du texte, l'ombrage du texte peut vraiment rehausser la conception de votre document.

## Prérequis

Avant de plonger dans le code, vous devez configurer quelques éléments pour suivre ce tutoriel. Voici ce dont vous aurez besoin :

1.  Aspose.PDF pour .NET : Assurez-vous d'avoir téléchargé et installé la dernière version d'Aspose.PDF. Vous pouvez[téléchargez-le ici](https://releases.aspose.com/pdf/net/).
2. IDE (environnement de développement intégré) : vous pouvez utiliser n’importe quel IDE compatible .NET, mais Visual Studio est fortement recommandé.
3. Connaissances de base de C# : vous devez être familiarisé avec la syntaxe C# et l’environnement .NET.
4. Un exemple de fichier PDF : vous aurez besoin d'un exemple de fichier PDF pour travailler. Si vous n'en avez pas, vous pouvez créer un simple fichier PDF texte ou utiliser n'importe quel fichier existant pour la démonstration.
5.  Licence Aspose.PDF : Bien que vous puissiez essayer Aspose.PDF avec un[permis temporaire](https://purchase.aspose.com/temporary-license/), vous pouvez également explorer les fonctionnalités à l'aide d'un essai gratuit.

## Paquets d'importation

Avant de passer au code, vous devez importer les espaces de noms requis. Ceux-ci vous permettront de travailler avec des objets Aspose.PDF et de manipuler les paramètres de texte et de couleur dans vos documents PDF.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Décomposons le processus d'ajout d'ombrage au texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET en étapes faciles à gérer. Ne vous inquiétez pas, c'est plus simple qu'il n'y paraît !

## Étape 1 : Configurez votre répertoire de documents

Tout d'abord, vous devez définir l'emplacement de vos documents. Considérez-le comme le dossier dans lequel tous vos fichiers PDF seront stockés et dans lequel vous enregistrerez votre fichier nouvellement modifié.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à vos fichiers PDF. Cela permet de s'assurer que votre code sait où chercher et où enregistrer le document modifié.

## Étape 2 : charger un document PDF existant

Une fois que vous avez défini le répertoire de votre document, il est temps de charger le fichier PDF que vous souhaitez modifier. Dans cet exemple, nous utilisons un fichier nommé`"text_sample4.pdf"`.

```csharp
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
    // Passez à l'étape suivante...
}
```

 Le`Document` L'objet d'Aspose.PDF nous aidera à ouvrir et à travailler avec le PDF.

## Étape 3 : Rechercher un texte spécifique à l'aide d'un TextFragmentAbsorber

Pour appliquer un ombrage à une partie spécifique du texte, nous devons trouver ce texte dans le PDF. C'est là qu'intervient TextFragmentAbsorber. C'est comme un scanner qui absorbe le texte que vous souhaitez modifier.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
```

 Dans cet exemple, nous recherchons la phrase « Lorem ipsum » dans le PDF.`Accept` la méthode traite les pages et permet à l'absorbeur d'identifier les fragments de texte.

## Étape 4 : Accédez au fragment de texte que vous souhaitez modifier

Maintenant que le texte a été absorbé, vous pouvez accéder au TextFragment spécifique. Nous supposons que la première occurrence du texte « Lorem ipsum » est ce que nous voulons modifier.

```csharp
TextFragment textFragment = absorber.TextFragments[1];
```

Cette ligne récupère la première instance de l'expression « Lorem ipsum » de la collection TextFragments. Vous pouvez modifier l'index si vous souhaitez modifier une autre instance.

## Étape 5 : appliquer l'ombrage au texte

Voici la partie amusante ! Ajoutons quelques couleurs d'ombrage au texte. Vous pouvez créer une nouvelle couleur avec un effet de dégradé à l'aide de GradientAxialShading. Dans cet exemple, nous allons appliquer un ombrage qui passe du rouge au bleu.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
    PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

 Cela crée un dégradé doux du rouge au bleu dans le texte sélectionné.`PatternColorSpace` est utilisé pour définir cet effet de couleur spécial.

## Étape 6 : Soulignez le texte (facultatif)

 Si vous souhaitez ajouter un soulignement au texte pour plus d'emphase, vous pouvez le faire en définissant le`Underline` propriété à`true`.

```csharp
textFragment.TextState.Underline = true;
```

L'ajout d'un soulignement peut rendre votre texte ombré encore plus visible.

## Étape 7 : Enregistrer le document PDF mis à jour

Enfin, une fois l’ombrage et toutes les autres modifications souhaitées appliqués, enregistrez le PDF dans le répertoire.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

 Le PDF modifié sera enregistré avec le nom`"text_out.pdf"`dans le répertoire que vous avez spécifié précédemment. Maintenant, vous pouvez ouvrir le fichier et voir votre texte magnifiquement ombré !

## Conclusion

Et voilà ! En quelques étapes simples, vous avez appliqué avec succès un ombrage au texte d'un PDF à l'aide d'Aspose.PDF pour .NET. Non seulement cette fonctionnalité permet de mettre en valeur un texte spécifique, mais elle ajoute également une touche professionnelle et soignée à vos documents. Que vous créiez des rapports visuellement attrayants ou que vous ayez simplement besoin de faire ressortir certaines parties de votre texte, cette technique change la donne.


## FAQ

### Puis-je appliquer un ombrage à plusieurs fragments de texte à la fois ?
Oui ! En parcourant la collection TextFragments, vous pouvez appliquer un ombrage à chaque fragment individuellement.

### Est-il possible de personnaliser les couleurs du dégradé ?
Absolument ! Vous pouvez définir toutes les couleurs que vous souhaitez pour le dégradé à l'aide de GradientAxialShading.

### Ai-je besoin d'une licence payante pour utiliser cette fonctionnalité ?
 Vous pouvez essayer cette fonctionnalité en utilisant un[essai gratuit](https://releases.aspose.com/) ou un[permis temporaire](https://purchase.aspose.com/temporary-license/), mais pour une fonctionnalité complète, une licence payante est recommandée.

### Comment puis-je changer le style de police du texte ?
 Vous pouvez modifier des propriétés telles que la taille, le style et le poids de la police via l'objet TextState en définissant des propriétés telles que`FontSize` et`FontStyle`.

### Puis-je ajouter un ombrage au texte nouvellement ajouté ?
Oui, vous pouvez ajouter un nouveau texte à un PDF et appliquer un ombrage en utilisant la même méthode décrite dans ce guide.