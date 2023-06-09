---
title: Déterminer le mot de passe correct
linktitle: Déterminer le mot de passe correct
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à déterminer le mot de passe correct pour un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-security-and-signatures/determine-correct-password/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de détermination du mot de passe correct pour un fichier PDF à l'aide d'Aspose.PDF pour .NET. Cette fonctionnalité vous permet de vérifier si un fichier PDF est protégé par mot de passe et de trouver le mot de passe correct dans une liste prédéfinie.

## Étape 1 : Prérequis

Avant de commencer, assurez-vous d'avoir les prérequis suivants :

- Connaissance de base du langage de programmation C#
- Installation de Visual Studio sur votre machine
- Bibliothèque Aspose.PDF pour .NET installée

## Étape 2 : Configuration de l'environnement

Pour commencer, procédez comme suit pour configurer votre environnement de développement :

1. Ouvrez Visual Studio et créez un nouveau projet C#.
2. Importez les espaces de noms requis dans votre fichier de code :

```csharp
using Aspose.Pdf;
```

## Étape 3 : Chargement du fichier PDF source

La première étape consiste à télécharger le fichier PDF source que vous souhaitez vérifier. Dans cet exemple, nous supposons que vous avez un fichier PDF nommé "IsPasswordProtected.pdf" dans le répertoire spécifié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Assurez-vous de remplacer les espaces réservés par les emplacements réels de votre fichier PDF.

## Étape 4 : déterminer le cryptage du PDF source

 Une fois que vous avez téléchargé le fichier PDF source, vous pouvez déterminer s'il est crypté à l'aide du`IsEncrypted` méthode de la`PdfFileInfo` objet.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

Cette déclaration indique si le fichier PDF est protégé par mot de passe ou non.

## Étape 5 : Trouver le bon mot de passe

Ensuite, nous rechercherons le mot de passe correct à l'aide d'une liste prédéfinie de mots de passe. Nous passons en revue chaque mot de passe de la liste et essayons de charger le document PDF avec ce mot de passe.

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

Cette boucle teste chaque mot de passe de la liste. Si le mot de passe est correct, le nombre de pages du document s'affiche. Sinon, un message indiquant que le mot de passe n'est pas correct s'affiche.


### Exemple de code source pour déterminer le mot de passe correct à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Charger le fichier PDF source
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
// Déterminer si le PDF source est crypté
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## Conclusion

Félicitation ! Vous avez déterminé avec succès le mot de passe correct pour un fichier PDF en utilisant Aspose.PDF pour .NET. Ce didacticiel a couvert le processus étape par étape, de la vérification du cryptage des fichiers à la recherche du mot de passe correct dans une liste prédéfinie. Vous pouvez maintenant utiliser cette fonction pour vérifier et trouver le mot de passe correct de vos fichiers PDF.