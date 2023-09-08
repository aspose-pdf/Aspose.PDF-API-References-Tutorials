---
title: Intégrer la police dans un fichier PDF
linktitle: Intégrer la police dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment intégrer des polices dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape. Assurez-vous que vos documents s’affichent correctement sur n’importe quel appareil.
type: docs
weight: 120
url: /fr/net/programming-with-document/embedfont/
---
Dans ce didacticiel, nous verrons comment intégrer des polices dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, modifier et manipuler des documents PDF par programme. Cette bibliothèque offre un large éventail de fonctionnalités pour travailler avec des documents PDF, notamment l'ajout de texte, d'images, de tableaux et bien plus encore. L'intégration de polices dans un fichier PDF est une exigence courante pour les développeurs qui souhaitent s'assurer que le fichier PDF s'affiche correctement sur différents appareils, que les polices requises soient installées ou non sur ces appareils.

## Étape 1 : Créer une nouvelle application console C#
Pour commencer, créez une nouvelle application console C# dans Visual Studio. Vous pouvez le nommer comme vous le souhaitez. Une fois le projet créé, vous devez ajouter une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer l'espace de noms Aspose.PDF
Ajoutez la ligne de code suivante en haut de votre fichier C# pour importer l'espace de noms Aspose.PDF :

```csharp
using Aspose.Pdf;
```

## Étape 3 : Charger un fichier PDF existant
Pour intégrer des polices dans un fichier PDF existant, vous devez charger ce fichier à l'aide de la classe Document. Le code suivant montre comment charger un fichier PDF existant :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger un fichier PDF existant
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 4 : Parcourir toutes les pages
Une fois que vous avez chargé le fichier PDF, vous devez parcourir toutes les pages du document. Pour chaque page, vous devez vérifier si des polices sont utilisées et, si tel est le cas, vous devez intégrer ces polices. Le code suivant montre comment parcourir toutes les pages du fichier PDF et intégrer les polices :

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            // Vérifiez si la police est déjà intégrée
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    // Rechercher les objets Form
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                // Vérifiez si la police est intégrée
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## Étape 5 : Enregistrez le document PDF
Une fois que vous avez intégré toutes les polices dans le fichier PDF, vous devez enregistrer le document. Le code suivant montre comment enregistrer le fichier PDF :

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### Exemple de code source pour Embed Font utilisant Aspose.PDF pour .NET

Voici le code source complet pour intégrer une police à l'aide d'Aspose.PDF pour .NET.


```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger un fichier PDF existant
Document doc = new Document(dataDir + "input.pdf");

// Parcourez toutes les pages
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Vérifiez si la police est déjà intégrée
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	// Rechercher les objets Form
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				// Vérifiez si la police est intégrée
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## Conclusion intégrer la police dans le fichier PDF
Dans cet article, nous avons expliqué comment intégrer des polices dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Aspose.PDF pour .NET fournit une API simple et facile à utiliser pour travailler avec des documents PDF, y compris l'ajout et l'intégration de polices. L'intégration de polices dans un fichier PDF est une étape importante pour garantir que le document s'affiche correctement sur différents appareils, que les polices requises soient installées ou non sur ces appareils.

### FAQ

#### Q : Pourquoi est-il important d'incorporer des polices dans un fichier PDF ?

R : L'intégration de polices dans un fichier PDF est essentielle pour garantir que le document s'affiche correctement sur différents appareils et systèmes. Lorsque les polices sont intégrées, elles font partie du fichier PDF, éliminant ainsi la dépendance aux polices externes installées sur le périphérique de visualisation.

#### Q : Puis-je intégrer toutes les polices utilisées dans un fichier PDF ?

R : Oui, vous pouvez intégrer toutes les polices utilisées dans un fichier PDF. Aspose.PDF pour .NET fournit une approche simple pour parcourir toutes les polices utilisées dans un fichier PDF et les intégrer pour garantir un rendu précis sur différents appareils.

#### Q : Aspose.PDF pour .NET est-il compatible avec différents formats de police ?

R : Oui, Aspose.PDF pour .NET prend en charge différents formats de police, notamment les polices TrueType, OpenType, Type 1 et CFF. Il peut intégrer des polices dans le fichier PDF quel que soit leur format.

#### Q : L'intégration de polices augmente-t-elle la taille du fichier PDF ?

R : Oui, l'intégration de polices dans un document PDF peut augmenter la taille du fichier, car les données de police sont incluses dans le fichier PDF lui-même. Toutefois, cela garantit que l'apparence du document reste cohérente, quelle que soit la disponibilité des polices sur le périphérique de visualisation.

#### Q : Puis-je personnaliser le processus d’intégration des polices ?

R : Oui, Aspose.PDF pour .NET vous permet de personnaliser le processus d'intégration des polices. Vous pouvez choisir les polices à intégrer, exclure des polices spécifiques ou intégrer uniquement des sous-ensembles spécifiques d'une police pour optimiser la taille du fichier.