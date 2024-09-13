---
title: Signer numériquement avec horodatage dans un fichier PDF
linktitle: Signer numériquement avec horodatage dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment signer numériquement un PDF avec un horodatage à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape couvre les prérequis, la configuration du certificat, l'horodatage et bien plus encore.
type: docs
weight: 50
url: /fr/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Introduction

Avez-vous déjà eu besoin de signer numériquement un PDF et d'inclure un horodatage pour plus de sécurité ? Que vous travailliez sur des documents juridiques, des contrats ou tout ce qui nécessite une authentification sécurisée, une signature numérique avec un horodatage ajoute une couche de crédibilité supplémentaire. Dans ce tutoriel, nous allons vous expliquer comment utiliser Aspose.PDF pour .NET pour ajouter une signature numérique ainsi qu'un horodatage à vos documents PDF. Ne vous inquiétez pas, nous allons procéder étape par étape !

## Prérequis

Avant de nous plonger dans le code, vous devez configurer quelques éléments pour pouvoir suivre le cours. Voici une liste de contrôle rapide des prérequis pour vous aider à démarrer :

-  Bibliothèque Aspose.PDF pour .NET : vous aurez besoin de la bibliothèque Aspose.PDF pour .NET installée dans votre projet. Vous pouvez[téléchargez la dernière version ici](https://releases.aspose.com/pdf/net/) ou ajoutez-le à votre projet via NuGet.
- Un document PDF : vous aurez besoin d'un fichier PDF d'exemple avec lequel travailler. Assurez-vous d'avoir un fichier dans le répertoire de votre projet que vous souhaitez signer.
-  Certificat numérique (fichier PFX) : assurez-vous de disposer d'un certificat numérique (un`.pfx` (fichier) pour signer numériquement le document.
- URL d'horodatage : il s'agit d'un service d'horodatage en ligne qui sera utilisé pour joindre un horodatage à la signature numérique. 
- Connaissances de base de C# : vous n’avez pas besoin d’être un expert, mais connaître les bases de C# vous aidera à comprendre et à personnaliser le code.

Une fois que vous avez coché toutes ces cases, vous êtes prêt à commencer à coder !

## Paquets d'importation

Pour commencer, vous devez importer les espaces de noms suivants dans votre projet C#. Cela vous garantit d'avoir accès aux classes et fonctions Aspose.PDF pertinentes.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Étape 1 : Charger le document PDF

La première chose à faire est de charger le document PDF que nous souhaitons signer. Voici comment procéder :

```csharp
// Définissez le chemin d’accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document PDF
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Cette étape est assez simple. Nous définissons simplement le chemin d'accès au document que nous souhaitons signer.`Document` la classe d'Aspose.PDF gère le chargement du fichier.

## Étape 2 : Configurer la signature numérique

Ensuite, nous allons créer la signature numérique à l'aide de la classe PKCS7 et charger le fichier PFX. Ce fichier PFX contient votre certificat et votre clé privée, qui sont nécessaires pour signer le document.

```csharp
// Chemin vers votre fichier .pfx
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Initialiser l'objet signature
PdfFileSignature signature = new PdfFileSignature(document);

// Charger le fichier PFX avec un mot de passe
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 À ce stade, vous indiquez à Aspose d'utiliser votre certificat numérique pour signer le document.`PKCS7`L'objet gère tout le travail cryptographique pour vous, vous n'avez donc pas à vous soucier des détails.

## Étape 3 : ajouter les paramètres d’horodatage

L'un des éléments clés d'une signature numérique robuste est l'horodatage. Il garantit que la signature du document peut être vérifiée même après l'expiration du certificat. Configurons l'horodatage à l'aide d'une autorité d'horodatage en ligne.

```csharp
// Définir les paramètres d'horodatage
TimestampSettings timestampSettings = new TimestampSettings("https://votre_url_horodatage", "utilisateur:mot_de_passe");

// Ajouter des paramètres d'horodatage à l'objet PKCS7
pkcs.TimestampSettings = timestampSettings;
```

Ici, vous spécifiez l'URL du service d'horodatage, qui fournira automatiquement une heure et une date à votre signature. Cela peut être fait avec ou sans authentification.

## Étape 4 : Définir l’emplacement et l’apparence de la signature

Nous allons maintenant définir l'emplacement de la signature dans le PDF ainsi que ses dimensions. Vous pouvez personnaliser la position de la zone de signature sur la page, ainsi que sa taille.

```csharp
//Définir l'apparence et l'emplacement de la signature (page 1, avec le rectangle spécifié)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Ici, nous définissons un rectangle qui positionne la signature aux coordonnées (100, 100) sur la première page du PDF, avec une largeur de 200 et une hauteur de 100. Vous pouvez modifier ces valeurs pour les adapter à votre conception.

## Étape 5 : Signez le document PDF

Une fois tout configuré, il est temps d'appliquer la signature numérique au PDF. Cette étape combine le certificat, l'horodatage et le positionnement en une seule commande simple.

```csharp
// Signez le document sur la première page
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Voici ce qui se passe :
- 1 : Ceci indique que la signature doit être appliquée sur la première page.
- « Raison de la signature » : c'est ici que vous pouvez spécifier pourquoi vous signez le document.
- « Contact » : saisissez les coordonnées du signataire.
- « Emplacement » : indiquez l’emplacement du signataire.
- vrai : Cette valeur booléenne indique si la signature est visible dans le document.
- rect : Le rectangle que nous avons défini précédemment spécifie la taille et la position de la signature.
- pkcs : l'objet PKCS7 contient les paramètres de certificat numérique et d'horodatage.

## Étape 6 : Enregistrer le PDF signé

Une fois le document signé, il ne vous reste plus qu'à l'enregistrer. Vous pouvez choisir un nouveau nom de fichier pour conserver à la fois l'original et la version signée.

```csharp
// Enregistrez le document PDF signé
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

Votre PDF nouvellement signé et horodaté est maintenant enregistré dans le répertoire spécifié !

## Conclusion

Et voilà ! Vous avez signé numériquement un PDF avec un horodatage à l'aide d'Aspose.PDF pour .NET. Ce processus garantit l'authenticité et l'intégrité de vos documents, ce qui vous offre, ainsi qu'au destinataire, une tranquillité d'esprit. Les signatures numériques deviennent de plus en plus essentielles dans le monde numérique d'aujourd'hui, il est donc indispensable de maîtriser ce processus.

## FAQ

### Puis-je utiliser un format de fichier différent pour le certificat ?  
Oui, mais le didacticiel se concentre sur l’utilisation d’un fichier PFX, qui est le format le plus courant pour les certificats numériques.

### Ai-je besoin d’une connexion Internet pour appliquer l’horodatage ?  
Oui, étant donné que l'horodatage est récupéré auprès d'une autorité d'horodatage en ligne, vous aurez besoin d'un accès Internet.

### Puis-je signer plusieurs pages dans un PDF ?  
 Absolument ! Vous pouvez modifier le`signature.Sign()` méthode pour cibler plusieurs pages ou parcourir toutes les pages.

### Que se passe-t-il si le mot de passe du fichier PFX est incorrect ?  
Vous recevrez une exception si le mot de passe est incorrect, assurez-vous donc qu'il est correctement saisi.

### Puis-je rendre la signature invisible ?  
 Oui, tu peux passer`false` au`Sign` paramètre de visibilité de la méthode pour rendre la signature invisible.