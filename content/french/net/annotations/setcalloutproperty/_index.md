---
title: Définir la propriété de légende dans un fichier PDF
linktitle: Définir la propriété de légende dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment définir la propriété de légende dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Personnalisez les annotations avec des lignes de légende, la couleur du texte et des styles de fin.
type: docs
weight: 130
url: /fr/net/annotations/setcalloutproperty/
---
 Aspose.PDF pour .NET est une bibliothèque puissante permettant de créer, manipuler et convertir des documents PDF en C#. L'une des fonctionnalités fournies par cette bibliothèque est la possibilité de définir des propriétés de légende pour les annotations de texte libre dans les documents PDF. Cela peut être fait en utilisant le`FreeTextAnnotation` classe, qui vous permet de créer des annotations avec des légendes.

Dans ce didacticiel, nous vous guiderons tout au long du processus de définition des propriétés de légende pour une annotation de texte libre à l'aide d'Aspose.PDF pour .NET en C#. Suivez les étapes ci-dessous pour commencer.

## Installer Aspose.PDF pour .NET

 Si vous ne l'avez pas déjà fait, vous devrez[télécharger](https://releases.aspose.com/pdf/net/) et installez Aspose.PDF pour .NET à partir des versions Aspose ou via le gestionnaire de packages NuGet.

## Étape 1 : Créer un nouveau document PDF

 Créez un nouveau document PDF à l'aide du`Document`classe fournie par Aspose.PDF pour .NET.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Étape 2 : Ajouter une nouvelle page au document

 Ajoutez une nouvelle page au document à l'aide du`Pages` collecte des`Document` classe.

```csharp
Page page = doc.Pages.Add();
```

## Étape 3 : Définir l'apparence par défaut

 Définissez l'apparence par défaut de l'annotation de texte libre en créant un nouveau`DefaultAppearance` objet et définir ses propriétés telles que`TextColor` et`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Étape 4 : Créez une annotation de texte libre avec légende

 Créez une nouvelle annotation de texte libre avec légende à l'aide de l'outil`FreeTextAnnotation` classe. Met le`Intent` propriété à`FreeTextIntent.FreeTextCallout` pour spécifier qu'il s'agit d'une annotation de légende. Met le`EndingStyle` propriété à`LineEnding.OpenArrow` pour spécifier le style de la flèche à la fin de la légende. Met le`Callout` propriété à un tableau de`Point` objets qui représentent les points de la page où la ligne de légende doit être tracée.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Étape 5 : Ajouter l'annotation de texte libre à la page

 Ajoutez l'annotation de texte libre à la page en utilisant le`Annotations` collecte des`Page` classe.

```csharp
page.Annotations.Add(fta);
```

## Étape 6 : ajouter du texte à l'annotation

 Ajoutez du texte à l'annotation en définissant le`RichText`propriété en une chaîne de XML formaté. Dans ce didacticiel, nous définissons la couleur du texte sur rouge et la taille de la police sur 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"couleur:#FF
```

## Étape 7 : enregistrez le document

Enregistrez maintenant le document en utilisant le code suivant :

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Exemple de code source pour définir la propriété de légende à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Ceci est un exemple</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment définir les propriétés de légende pour une annotation de texte libre dans un document PDF à l'aide d'Aspose.PDF pour .NET. Les annotations de légende sont utiles pour fournir des informations supplémentaires ou des explications liées à des zones spécifiques d'un document. Aspose.PDF pour .NET offre un large éventail de fonctionnalités et de capacités pour travailler avec des fichiers PDF, notamment la création et la personnalisation d'annotations, telles que des légendes. En suivant le guide étape par étape et en utilisant le code source C# fourni, les développeurs peuvent facilement implémenter des annotations de légende dans leurs documents PDF, améliorant ainsi la convivialité et la clarté de leurs documents. Aspose.PDF for .NET est une bibliothèque polyvalente et fiable pour les opérations PDF dans les applications .NET, offrant des outils puissants pour gérer efficacement diverses tâches liées aux PDF.

### FAQ pour définir la propriété de légende dans un fichier PDF

#### Q : Qu'est-ce qu'une annotation de légende dans un document PDF ?

R : Une annotation de légende dans un document PDF est un type d'annotation qui vous permet de créer une zone de texte avec une ligne de repère pointant vers une zone spécifique du document. Il est couramment utilisé pour fournir des informations supplémentaires ou des commentaires liés à une section ou un élément particulier du document.

#### Q : Puis-je personnaliser l'apparence de l'annotation de légende à l'aide d'Aspose.PDF pour .NET ?

R : Oui, vous pouvez personnaliser diverses propriétés de l'annotation de légende, telles que la couleur, la taille de la police, l'alignement du texte, le style de ligne, le style de flèche, etc.

#### Q : Comment ajouter du texte à l'annotation de légende ?

 R : Pour ajouter du texte à l'annotation de légende, vous pouvez définir le`RichText` propriété du`FreeTextAnnotation` objet. Le`RichText` La propriété prend une chaîne XML formatée qui représente le texte à afficher dans l'annotation de légende.

#### Q : Puis-je ajouter plusieurs annotations de légende à un document PDF à l'aide d'Aspose.PDF pour .NET ?

 R : Oui, vous pouvez créer plusieurs annotations de légende dans un document PDF en créant plusieurs instances du`FreeTextAnnotation`objet et en les ajoutant à différentes pages ou emplacements du document.