---
title: Supprimer les hyperliens après la conversion à partir de HTML
linktitle: Supprimer les hyperliens après la conversion à partir de HTML
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment supprimer les hyperliens des documents HTML après la conversion au format PDF à l'aide d'Aspose.PDF pour .NET dans ce guide étape par étape.
type: docs
weight: 250
url: /fr/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## Introduction

À l'ère du numérique, la conversion de documents HTML en PDF est une tâche courante. Cependant, vous souhaiterez peut-être parfois supprimer les hyperliens du PDF converti pour diverses raisons, telles que l'amélioration de la lisibilité ou la prévention d'une navigation indésirable. Dans ce didacticiel, nous verrons comment y parvenir à l'aide d'Aspose.PDF pour .NET. 

## Prérequis

Avant de plonger dans le code, assurez-vous de disposer des prérequis suivants :

1. Visual Studio : assurez-vous que Visual Studio est installé sur votre ordinateur. Il s'agira de votre environnement de développement.
2.  Aspose.PDF pour .NET : vous devez disposer de la bibliothèque Aspose.PDF. Vous pouvez la télécharger à partir de[ici](https://releases.aspose.com/pdf/net/).
3. Connaissances de base de C# : la familiarité avec la programmation C# vous aidera à mieux comprendre le code.

## Paquets d'importation

Pour commencer, vous devez importer les packages nécessaires dans votre projet C#. Voici comment procéder :

1. Ouvrez votre projet Visual Studio.
2. Cliquez avec le bouton droit sur votre projet dans l'Explorateur de solutions et sélectionnez « Gérer les packages NuGet ».
3.  Rechercher`Aspose.PDF` et installez-le.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Maintenant que vous avez tout configuré, décomposons le processus de suppression des hyperliens d'un fichier HTML après l'avoir converti en PDF.

## Étape 1 : Configurer le répertoire de documents

Tout d'abord, vous devez spécifier le chemin d'accès à votre répertoire de documents. C'est là que se trouve votre fichier HTML et où le PDF de sortie sera enregistré.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où votre fichier HTML est stocké.

## Étape 2 : Charger le document HTML

 Ensuite, vous chargerez le document HTML à l’aide de la`Document` classe d'Aspose.PDF. Cette classe vous permet de travailler facilement avec des documents PDF.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 Ici, nous chargeons le fichier HTML nommé`SampleHtmlFile.html`Assurez-vous que ce fichier existe dans le répertoire spécifié.

## Étape 3 : Enregistrer le document dans le flux mémoire

Avant de commencer à traiter les annotations, nous devons enregistrer le document dans un flux de mémoire. Cette étape est cruciale car elle prépare le document à une manipulation ultérieure.

```csharp
doc.Save(new MemoryStream());
```

Cette ligne enregistre le document en mémoire, nous permettant de travailler avec lui sans l'écrire sur le disque pour l'instant.

## Étape 4 : parcourir les annotations

Nous allons maintenant parcourir les annotations du document. Les annotations sont des éléments tels que des liens, des commentaires et des surlignements. Nous nous intéressons plus particulièrement aux annotations de liens.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // Traiter l'annotation du lien
    }
}
```

Dans cette boucle, nous vérifions si le type d'annotation est un lien. Si c'est le cas, nous passons aux étapes suivantes.

## Étape 5 : Supprimer l'action de lien hypertexte

Pour chaque annotation de lien, nous devons vérifier si elle possède une action d'hyperlien. Si c'est le cas, nous supprimerons l'hyperlien en définissant son URI sur une chaîne vide.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

Cet extrait de code garantit que l’action du lien hypertexte est effectivement supprimée.

## Étape 6 : Absorber les fragments de texte

Ensuite, nous allons absorber les fragments de texte associés à l'annotation du lien. Cela nous permet de manipuler l'apparence du texte.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 Ici, nous créons un`TextFragmentAbsorber` et définissez ses options de recherche sur le rectangle de l'annotation. Cela nous aide à trouver le texte qui a été lié.

## Étape 7 : Modifier l’apparence du texte

Une fois que nous avons les fragments de texte, nous pouvons modifier leur apparence. Dans ce cas, nous supprimerons le soulignement et changerons la couleur du texte en noir.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

Cette étape améliore la lisibilité du texte en supprimant le style du lien hypertexte.

## Étape 8 : supprimer l’annotation

Après avoir modifié le texte, nous pouvons supprimer en toute sécurité l’annotation du lien du document.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

Cette ligne supprime le lien hypertexte du PDF, garantissant qu'il n'existe plus dans la sortie finale.

## Étape 9 : Enregistrer le document modifié

Enfin, nous devons enregistrer le document modifié dans un nouveau fichier PDF. C'est la dernière étape de notre processus.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Cette ligne enregistre le document avec les hyperliens supprimés, créant un nouveau fichier PDF nommé`RemoveHyperlinksFromText_out.pdf`.

## Conclusion

Et voilà ! Vous avez réussi à supprimer les hyperliens d'un document HTML après l'avoir converti en PDF à l'aide d'Aspose.PDF pour .NET. Ce processus améliore non seulement la lisibilité de votre PDF, mais vous donne également le contrôle sur le contenu que vous présentez. 

## FAQ

### Puis-je supprimer des hyperliens de n’importe quel document PDF ?
Oui, vous pouvez supprimer les hyperliens de n’importe quel document PDF à l’aide d’Aspose.PDF pour .NET.

### L'utilisation d'Aspose.PDF est-elle gratuite ?
 Aspose.PDF propose un essai gratuit, mais pour bénéficier de toutes les fonctionnalités, vous devez acheter une licence.[page d'achat](https://purchase.aspose.com/buy).

### Que faire si je rencontre des problèmes lors de l’utilisation d’Aspose.PDF ?
 Vous pouvez demander de l'aide sur le[Forum de soutien](https://forum.aspose.com/c/pdf/10).

### Puis-je convertir d’autres formats de fichiers en PDF à l’aide d’Aspose ?
Oui, Aspose prend en charge différents formats de fichiers pour la conversion en PDF.

### Où puis-je télécharger Aspose.PDF pour .NET ?
 Vous pouvez le télécharger à partir du[lien de téléchargement](https://releases.aspose.com/pdf/net/).