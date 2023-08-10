---
title: Préserver les droits
linktitle: Préserver les droits
second_title: Référence de l'API Aspose.PDF pour .NET
description: Préservez les droits de formulaire dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 210
url: /fr/net/programming-with-forms/preserve-rights/
---
Dans ce didacticiel, nous allons vous montrer comment conserver les droits de formulaire dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'avoir importé les bibliothèques nécessaires et définissez le chemin d'accès à votre répertoire de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrez le document

 Ouvrez le document PDF source à l'aide d'un`FileStream` avec autorisation de lecture et d'écriture :

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Étape 3 : Modifier les champs du formulaire

Parcourez tous les champs de formulaire du document et apportez les modifications nécessaires. Dans cet exemple, nous modifions la valeur d'un champ de formulaire dont le nom contient "A1" :

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Étape 4 : Enregistrer le document mis à jour

Enregistrez le document PDF modifié :

```csharp
pdfDocument.Save();
```

##  Étape 5 : Fermez le`FileStream`

 N'oubliez pas de fermer le`FileStream` objet lorsque vous avez terminé :

```csharp
fs. Close();
```

### Exemple de code source pour préserver les droits à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Lire le formulaire PDF source avec FileAccess de lecture et d'écriture.
// Nous avons besoin de l'autorisation ReadWrite car après modification,
// Nous devons enregistrer le contenu mis à jour dans le même document/fichier.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Instancier l'instance de document
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Obtenir des valeurs de tous les champs
foreach (Field formField in pdfDocument.Form)
{
	// Si le nom complet du champ contient A1, effectuez l'opération
	if (formField.FullName.Contains("A1"))
	{
		// Convertir le champ de formulaire en TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Modifier la valeur du champ
		textBoxField.Value = "Testing";
	}
}
// Enregistrez le document mis à jour dans save FileStream
pdfDocument.Save();
// Fermer l'objet File Stream
fs.Close();
```

## Conclusion

Dans ce didacticiel, nous avons appris à préserver les droits d'un formulaire dans un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement accéder aux champs du formulaire et apporter des modifications spécifiques tout en préservant les autorisations d'accès et d'écriture.


### FAQ

#### Q : Puis-je conserver les droits de champs de formulaire spécifiques sans affecter les autres dans le document PDF ?

 R : Oui, en utilisant le`FullName` propriété des champs de formulaire, vous pouvez cibler des champs de formulaire spécifiques pour la préservation tout en laissant les autres inchangés.

#### Q : Puis-je conserver les droits d'un formulaire dans un document PDF protégé par un mot de passe ?

R : Oui, Aspose.PDF pour .NET vous permet de conserver les droits d'un formulaire même dans les documents PDF protégés par mot de passe, tant que vous fournissez le mot de passe correct pour accéder et modifier le fichier.

#### Q : Que se passe-t-il si j'essaie de modifier des champs de formulaire sans les droits d'accès appropriés ?

R : Si vous tentez de modifier des champs de formulaire sans les droits d'accès appropriés, les modifications ne seront pas enregistrées dans le document PDF et vous pourrez recevoir une exception ou un message d'erreur.

#### Q : Aspose.PDF pour .NET est-il compatible avec toutes les versions de .NET Framework ?

R : Oui, Aspose.PDF pour .NET est compatible avec toutes les versions de .NET Framework, y compris .NET Core et .NET Standard.

#### Q : Puis-je conserver les droits de formulaire dans un document PDF par programmation dans d'autres langages de programmation que C# ?

R : Oui, Aspose.PDF pour .NET prend en charge divers langages de programmation, tels que VB.NET et ASP.NET, en plus de C#.