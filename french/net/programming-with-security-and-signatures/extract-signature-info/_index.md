---
title: Extraire les informations de signature
linktitle: Extraire les informations de signature
second_title: Référence de l'API Aspose.PDF pour .NET
description: Extraction des informations de signature à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 80
url: /fr/net/programming-with-security-and-signatures/extract-signature-info/
---

Le processus d'extraction des informations de signature d'un document PDF peut être très utile dans divers scénarios. Que vous ayez besoin de valider l'authenticité d'un document signé ou d'analyser le certificat utilisé pour la signature, la bibliothèque Aspose.PDF pour .NET fournit une solution pratique. Dans ce didacticiel, nous vous guiderons pas à pas dans le processus d'extraction des informations de signature à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous que les conditions préalables suivantes sont en place :

1. Connaissance de base du langage de programmation C#.
2. Bibliothèque Aspose.PDF pour .NET installée sur votre système.
3. Un document PDF valide avec un ou plusieurs champs de signature.

Passons maintenant aux détails de la mise en œuvre.

## Étape 1 : Importation des bibliothèques requises

 Pour commencer, vous devez importer les bibliothèques nécessaires dans votre projet C#. Dans ce cas, nous devons importer le`Aspose.Pdf` et`System.IO` espaces de noms. Cela peut être fait en ajoutant le code suivant au début de votre fichier C# :

```csharp
using Aspose.Pdf;
using System.IO;
```

## Étape 2 : Définir le chemin du document

 Ensuite, vous devez définir le chemin d'accès au document PDF dont vous souhaitez extraire les informations de signature. Remplacer`"YOUR DOCUMENTS DIRECTORY"` dans l'extrait de code suivant avec le chemin d'accès réel à votre document :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Étape 3 : Extraction des informations de signature

Passons maintenant à la partie principale du code où nous extrayons les informations de signature du document PDF. Nous parcourons chaque champ du formulaire du document et vérifions s'il s'agit d'un champ de signature. Si un champ de signature est trouvé, nous procédons à l'extraction du certificat. Ajoutez l'extrait de code suivant :

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Extraire le certificat
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Étape 4 : Extraction du certificat

Dans cette étape, nous extrayons le certificat du champ de signature et l'enregistrons sous forme de fichier. Le certificat extrait peut être analysé plus en détail ou utilisé à des fins de validation. L'extrait de code ci-dessous illustre le processus d'extraction et d'enregistrement :

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Étape 5

: Sauvegarde du certificat

Enfin, nous enregistrons le certificat extrait sous forme de fichier. Dans cet exemple, le certificat est enregistré sous le nom "input.cer" dans le répertoire spécifié. Vous pouvez modifier le code en fonction de vos besoins. Voici l'extrait de code permettant d'enregistrer le certificat :

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

C'est ça! Vous avez extrait avec succès les informations de signature à l'aide d'Aspose.PDF pour .NET. N'hésitez pas à intégrer ce code dans vos propres applications ou à le modifier selon vos besoins.

### Exemple de code source pour Extraire les informations de signature à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Dans ce didacticiel, nous avons parcouru un guide étape par étape sur la façon d'extraire les informations de signature d'un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous avons couvert le processus d'importation des bibliothèques requises, la définition du chemin du document, l'extraction des informations de signature, l'extraction du certificat et son enregistrement dans un fichier. En suivant ces étapes, vous pouvez facilement récupérer les détails de la signature et les utiliser au besoin.