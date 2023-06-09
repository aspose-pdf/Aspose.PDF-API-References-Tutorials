---
title: Définir la propriété de la légende
linktitle: Définir la propriété de la légende
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir la propriété Callout à l'aide d'Aspose.PDF pour .NET. Personnalisez les annotations avec des lignes de légende, la couleur du texte et les styles de fin.
type: docs
weight: 130
url: /fr/net/annotations/setcalloutproperty/
---
 Aspose.PDF pour .NET est une bibliothèque puissante pour créer, manipuler et convertir des documents PDF en C#. L'une des fonctionnalités fournies par cette bibliothèque est la possibilité de définir des propriétés de légende pour les annotations de texte libre dans les documents PDF. Ceci peut être fait en utilisant le`FreeTextAnnotation` class, qui vous permet de créer des annotations avec des légendes.

Dans ce didacticiel, nous vous guiderons tout au long du processus de définition des propriétés de légende pour une annotation de texte libre à l'aide d'Aspose.PDF pour .NET en C#. Suivez les étapes ci-dessous pour commencer.

## Installer Aspose.PDF pour .NET

 Si vous ne l'avez pas déjà fait, vous devrez[télécharger](https://releases.aspose.com/pdf/net/) et installez Aspose.PDF pour .NET à partir des versions d'Aspose ou via le gestionnaire de packages NuGet.

## Étape 1 : Créer un nouveau document PDF

 Créez un nouveau document PDF à l'aide de`Document` classe fournie par Aspose.PDF pour .NET.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Étape 2 : Ajouter une nouvelle page au document

 Ajoutez une nouvelle page au document à l'aide de la`Pages` collecte de la`Document` classe.

```csharp
Page page = doc.Pages.Add();
```

## Étape 3 : Définir l'apparence par défaut

 Définissez l'apparence par défaut de l'annotation de texte libre en créant un nouveau`DefaultAppearance` objet et la définition de ses propriétés telles que`TextColor` et`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Étape 4 : Créer une annotation de texte libre avec légende

 Créez une nouvelle annotation de texte libre avec légende à l'aide de la`FreeTextAnnotation` classe. Met le`Intent` propriété à`FreeTextIntent.FreeTextCallout` pour spécifier qu'il s'agit d'une annotation de légende. Met le`EndingStyle` propriété à`LineEnding.OpenArrow` pour spécifier le style de la flèche à la fin de la légende. Met le`Callout` propriété à un tableau de`Point` objets qui représentent les points sur la page où la ligne de légende doit être tracée.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Étape 5 : Ajoutez l'annotation de texte libre à la page

 Ajoutez l'annotation de texte libre à la page en utilisant le`Annotations` collecte de la`Page` classe.

```csharp
page.Annotations.Add(fta);
```

## Étape 6 : Ajouter du texte à l'annotation

Ajoutez du texte à l'annotation en définissant le`RichText` propriété à une chaîne de XML formaté. Dans ce didacticiel, nous définissons la couleur du texte sur le rouge et la taille de la police sur 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## Étape 7 : enregistrez le document

Enregistrez maintenant le document en utilisant le code suivant :

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Exemple de code source pour Set Callout Property à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
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
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Ceci est un exemple</span></p></body>" ;
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
