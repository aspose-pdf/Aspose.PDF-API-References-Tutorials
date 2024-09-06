---
title: Extraire le texte en surbrillance dans un fichier PDF
linktitle: Extraire le texte en surbrillance dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire efficacement le texte en surbrillance d'un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce didacticiel. Idéal pour l'analyse de données et la révision de contenu.
type: docs
weight: 60
url: /fr/net/annotations/extracthighlightedtext/
---
## Introduction

Lorsque vous travaillez avec des fichiers PDF, l'extraction du texte mis en surbrillance peut être une tâche cruciale, que ce soit pour l'analyse des données, la révision du contenu ou simplement l'organisation de vos notes. Si vous utilisez Aspose.PDF pour .NET, ce processus est simple et efficace. Dans ce didacticiel, nous vous expliquerons comment extraire le texte mis en surbrillance d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous aborderons tous les aspects, des conditions préalables aux instructions étape par étape, pour vous assurer d'avoir une compréhension complète à la fin.

## Prérequis

Avant de plonger dans le code, vous devez mettre en place quelques éléments :

-  Bibliothèque Aspose.PDF pour .NET : assurez-vous que la bibliothèque Aspose.PDF est installée. Si ce n'est pas le cas, vous pouvez la télécharger à partir du[page de sortie](https://releases.aspose.com/pdf/net/).
- Environnement de développement : vous devez disposer d’un environnement de développement fonctionnel configuré, tel que Visual Studio.
- Connaissances de base de C# : La familiarité avec le langage de programmation C# et la programmation orientée objet est essentielle.
-  Une licence Aspose valide : bien que vous puissiez commencer par un essai gratuit, envisagez d'obtenir une[permis temporaire](https://purchase.aspose.com/temporary-license/) ou en acheter un chez[ici](https://purchase.aspose.com/buy) pour une utilisation sans restriction.

## Paquets d'importation

Pour commencer, vous devez importer les espaces de noms nécessaires dans votre projet C#. Cela est essentiel pour accéder aux classes et méthodes fournies par Aspose.PDF pour .NET.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Maintenant, décomposons le processus d'extraction du texte en surbrillance d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Chaque étape est expliquée en détail pour vous aider à comprendre les concepts sous-jacents et leur mise en œuvre.

## Étape 1 : Configurez votre répertoire de projet

Tout d’abord, vous devez configurer le répertoire de votre projet dans lequel se trouve votre fichier PDF. C’est là que la magie opère.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin d'accès réel vers votre répertoire où se trouve le fichier PDF. C'est dans ce répertoire que l'application récupérera le PDF pour le traitement.

## Étape 2 : Charger le document PDF

 Ensuite, vous devez charger le document PDF à partir duquel vous souhaitez extraire le texte surligné. Cela se fait à l'aide de l'`Document` cours fourni par Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

 Le`Document` la classe est instanciée avec le chemin d'accès au fichier PDF. Ici,`"ExtractHighlightedText.pdf"` est le nom du fichier PDF qui contient le texte surligné. Assurez-vous que ce fichier existe dans le répertoire spécifié.

## Étape 3 : Accéder à la collection d'annotations

Une fois le document PDF chargé, l'étape suivante consiste à accéder aux annotations sur la première page du document. Les annotations sont utilisées dans les PDF pour ajouter des informations supplémentaires telles que des surlignements, des commentaires, etc.

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
```

 Le`Annotations` propriété de la`Page` L'objet donne accès à toutes les annotations d'une page particulière du PDF. Ici, nous parcourons chaque annotation de la première page.

## Étape 4 : Filtrer les annotations de texte en surbrillance

Maintenant que nous avons accès à toutes les annotations, nous devons filtrer uniquement les annotations de texte en surbrillance. Pour cela, il faut vérifier le type de chaque annotation.

```csharp
if (annotation is TextMarkupAnnotation)
{
    TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

 Le`TextMarkupAnnotation` La classe est utilisée pour représenter les annotations de balisage de texte, y compris les surlignements.`is` le mot-clé vérifie si l'annotation est de type`TextMarkupAnnotation` , et si c'est le cas, il convertit l'annotation en`TextMarkupAnnotation`.

## Étape 5 : Extraire le texte en surbrillance

Une fois l’annotation en surbrillance identifiée, l’étape suivante consiste à extraire le texte associé à la surbrillance.

```csharp
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
foreach (TextFragment tf in collection)
{
    Console.WriteLine(tf.Text);
}
```

 Le`GetMarkedTextFragments()` la méthode renvoie une collection de`TextFragment` objets, chacun représentant une partie du texte mis en surbrillance. Nous parcourons cette collection et imprimons le texte de chaque fragment sur la console.

## Conclusion

L'extraction de texte surligné d'un PDF à l'aide d'Aspose.PDF pour .NET est une fonctionnalité puissante qui peut rationaliser votre flux de travail, en particulier si vous traitez des documents volumineux. En suivant les étapes décrites dans ce didacticiel, vous pouvez facilement implémenter cette fonctionnalité dans vos propres projets. Que vous organisiez vos notes, prépariez des rapports ou effectuiez une analyse de données, cette méthode offre une solution transparente pour extraire et utiliser du texte surligné.

## FAQ

### Puis-je extraire d’autres types d’annotations en utilisant cette méthode ?  
 Oui, vous pouvez extraire d'autres types d'annotations en modifiant le`if` condition pour vérifier différents types d'annotations, tels que`TextAnnotation`, `StampAnnotation`, etc.

### Est-il possible d'extraire le texte en surbrillance de toutes les pages du PDF ?  
Absolument ! Vous pouvez parcourir chaque page du document PDF et appliquer la même logique d'extraction pour rassembler le texte mis en surbrillance sur chaque page.

### Ai-je besoin d'une licence pour utiliser Aspose.PDF pour .NET ?  
 Bien que vous puissiez commencer avec un essai gratuit, il est recommandé d'obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/)ou achetez une licence complète pour un accès illimité à toutes les fonctionnalités.

### Puis-je enregistrer le texte extrait dans un fichier au lieu de l’imprimer sur la console ?  
Oui, vous pouvez facilement modifier le code pour enregistrer le texte extrait dans un fichier texte ou tout autre format souhaité.

### Aspose.PDF prend-il en charge d’autres plates-formes en plus de .NET ?  
Oui, Aspose.PDF prend également en charge Java et d'autres plates-formes, offrant des fonctionnalités similaires dans différents environnements.