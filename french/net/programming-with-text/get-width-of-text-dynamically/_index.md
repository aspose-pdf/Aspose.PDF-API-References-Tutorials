---
title: Obtenir dynamiquement la largeur du texte
linktitle: Obtenir dynamiquement la largeur du texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à obtenir dynamiquement la largeur du texte à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 220
url: /fr/net/programming-with-text/get-width-of-text-dynamically/
---

Dans ce tutoriel, nous expliquerons comment utiliser Aspose.PDF pour .NET pour mesurer dynamiquement la largeur du texte en C#. Cela peut être utile lorsque vous devez déterminer la taille d'une chaîne de texte avant de la rendre sur un document PDF. Nous vous guiderons étape par étape à travers le code source C# fourni.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Bibliothèque Aspose.PDF pour .NET installée.
- Visual Studio ou tout autre environnement de développement C#.

## Étape 1 : Définir le répertoire de documents

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin du répertoire où se trouvent vos documents. Il sera utilisé pour stocker tous les fichiers PDF générés.

## Étape 2 : Trouver la police

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
```

 Le code ci-dessus trouve la police Arial en utilisant le`FindFont` méthode de la`FontRepository` classe. Si vous souhaitez utiliser une police différente, remplacez`"Arial"` avec le nom de police souhaité.

## Étape 3 : Définir l'état du texte

```csharp
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
```

 Ici, nous créons un nouveau`TextState` objet et définissez ses propriétés. Nous attribuons la police précédemment trouvée (`font`) et définissez la taille de la police sur 14. Ajustez la taille de la police selon vos besoins.

## Étape 4 : mesurer la largeur du texte

```csharp
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```

Le code ci-dessus montre comment mesurer la largeur du texte en utilisant directement la police (`font.MeasureString`) et l'état du texte (`ts.MeasureString`). Il comprend des contrôles de validation pour s'assurer que les mesures sont exactes.

### Exemple de code source pour obtenir dynamiquement la largeur du texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```


## Conclusion

Vous avez appris à utiliser Aspose.PDF pour .NET pour mesurer dynamiquement la largeur du texte en C#. En suivant les étapes décrites dans ce didacticiel, vous pouvez déterminer avec précision la largeur des chaînes de texte avant de les afficher dans un document PDF.