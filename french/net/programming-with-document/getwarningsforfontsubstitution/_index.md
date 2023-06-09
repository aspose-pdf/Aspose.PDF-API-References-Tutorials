---
title: Obtenir des avertissements pour la substitution de polices
linktitle: Obtenir des avertissements pour la substitution de polices
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser la fonctionnalité GetWarningsForFontSubstitution d'Aspose.PDF pour .NET pour détecter les avertissements de substitution de polices lors de l'ouverture d'un document PDF.
type: docs
weight: 190
url: /fr/net/programming-with-document/getwarningsforfontsubstitution/
---

 Aspose.PDF pour .NET est une bibliothèque de manipulation PDF populaire qui permet aux développeurs de créer, éditer et convertir des fichiers PDF dans leurs applications .NET. L'une des fonctionnalités offertes par cette bibliothèque est la capacité de détecter les avertissements de substitution de polices lors de l'ouverture d'un document PDF. Ce didacticiel vous guidera à travers les étapes d'utilisation de`GetWarningsForFontSubstitution` fonctionnalité d'Aspose.PDF pour .NET pour détecter les avertissements de substitution de police lors de l'ouverture d'un document PDF.

## Étape 1 : Installer Aspose.PDF pour .NET

 Pour utiliser Aspose.PDF pour .NET dans vos applications .NET, vous devez d'abord installer la bibliothèque. Vous pouvez télécharger la dernière version de la bibliothèque à partir du[Aspose.PDF pour la page de téléchargement .NET](https://relases.aspose.com/pdf/net).

Une fois que vous avez téléchargé la bibliothèque, extrayez le contenu du fichier ZIP dans un dossier sur votre ordinateur. Vous devrez ensuite ajouter une référence à la DLL Aspose.PDF pour .NET dans votre projet .NET.

## Étape 2 : Chargez le document PDF

 Une fois que vous avez installé Aspose.PDF pour .NET et ajouté une référence à la DLL dans votre projet .NET, vous pouvez commencer à utiliser le`GetWarningsForFontSubstitution` fonctionnalité pour détecter les avertissements de substitution de polices lors de l'ouverture d'un document PDF.

La première étape de l'utilisation de cette fonctionnalité consiste à charger le document PDF pour lequel vous souhaitez détecter les avertissements de substitution de police. Pour ce faire, vous pouvez utiliser le code suivant :

```csharp
// Le chemin d'accès au document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document PDF
Document doc = new Document(dataDir + "input.pdf");
```

 Dans le code ci-dessus, remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où se trouve votre document PDF. Ce code chargera le document PDF dans un`Document` objet, que vous pouvez ensuite utiliser pour détecter les avertissements de substitution de polices.

## Étape 3 : Détecter les avertissements de substitution de police

Pour détecter les avertissements de substitution de polices lors de l'ouverture d'un document PDF, vous pouvez utiliser le code suivant :

```csharp
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);
```

 Dans le code ci-dessus,`OnFontSubstitution` est une méthode qui sera appelée chaque fois qu'un avertissement de substitution de police est détecté. Vous pouvez personnaliser cette méthode pour gérer l'avertissement de substitution de police comme bon vous semble.

 Voici un exemple d'implémentation du`OnFontSubstitution` méthode:

```csharp
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```

 Dans le code ci-dessus, le`OnFontSubstitution` La méthode affiche simplement le nom de la police d'origine et le nom de la police de substitution dans la console chaque fois qu'un avertissement de substitution de police est détecté. Vous pouvez personnaliser cette méthode pour gérer l'avertissement de substitution de police comme bon vous semble.

### Exemple de code source pour obtenir des avertissements pour la substitution de polices à l'aide d'Aspose.NET pour PDF

 Voici le code source complet permettant de détecter les avertissements de substitution de polices lors de l'ouverture d'un document PDF à l'aide de`GetWarningsForFontSubstitution` fonctionnalité d'Aspose.PDF pour .NET :

```csharp
// Le chemin d'accès au document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document PDF
Document doc = new Document(dataDir + "input.pdf");

// Détecter les avertissements de substitution de polices
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);

// Gérer l'avertissement de substitution de police
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```