---
title: Signer avec une carte à puce à l'aide d'une signature de fichier PDF
linktitle: Signer avec une carte à puce à l'aide d'une signature de fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment signer des fichiers PDF à l'aide d'une carte à puce avec Aspose.PDF pour .NET. Suivez ce guide étape par étape pour des signatures numériques sécurisées.
type: docs
weight: 110
url: /fr/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## Introduction

À l'ère du numérique, la sécurisation des documents est plus cruciale que jamais. Qu'il s'agisse d'un contrat, d'un accord ou de toute information sensible, il est primordial de s'assurer que le document est authentique et n'a pas été falsifié. C'est là qu'interviennent les signatures numériques ! Aujourd'hui, nous allons découvrir comment signer un fichier PDF à l'aide d'une carte à puce avec Aspose.PDF pour .NET. Cette puissante bibliothèque permet aux développeurs de manipuler et de créer des documents PDF de manière efficace, notamment en ajoutant des signatures numériques sécurisées. Alors, prenez votre carte à puce et commençons !

## Prérequis

Avant de passer aux détails de la signature d'un fichier PDF, assurons-nous que vous disposez de tout ce dont vous avez besoin. Voici une liste de contrôle pour vous aider à vous préparer :

1.  Aspose.PDF pour .NET : Assurez-vous que la bibliothèque Aspose.PDF est installée. Vous pouvez la télécharger à partir du[site](https://releases.aspose.com/pdf/net/).
2. Visual Studio : un environnement de développement dans lequel vous pouvez écrire et exécuter votre code .NET.
3. Carte à puce : vous aurez besoin d'une carte à puce avec un certificat numérique valide installé.
4. Compréhension de base de C# : une familiarité avec la programmation C# sera bénéfique car nous écrirons des extraits de code dans ce langage.
5. Document PDF : un exemple de fichier PDF (comme`blank.pdf`) pour tester notre processus de signature.

Avec ces prérequis en place, vous êtes prêt à plonger dans le code !

## Paquets d'importation

Tout d'abord, importons les packages nécessaires. Vous devrez ajouter des références à la bibliothèque Aspose.PDF dans votre projet. Voici comment procéder :

1. Ouvrez Visual Studio.
2. Créez un nouveau projet ou ouvrez-en un existant.
3.  Cliquez avec le bouton droit sur votre projet dans l'explorateur de solutions et sélectionnez`Manage NuGet Packages`.
4.  Rechercher`Aspose.PDF` et installez la dernière version.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Maintenant que nous avons importé les packages nécessaires, décomposons le code étape par étape.

## Étape 1 : Configurez votre document

La première étape de notre processus consiste à configurer le document PDF que nous souhaitons signer. Voici comment procéder :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
 Dans cet extrait, nous définissons le chemin d'accès à notre répertoire de documents et créons une instance du`Document` classe utilisant un exemple de fichier PDF nommé`blank.pdf` Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel où se trouve votre PDF.

## Étape 2 : Initialiser PdfFileSignature

 Ensuite, nous allons initialiser le`PdfFileSignature` classe, qui est responsable de la gestion du processus de signature.

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
Ici, nous créons une instance de`PdfFileSignature`et liez-le à notre document PDF. Cela prépare le document pour la signature.

## Étape 3 : Accéder au certificat de la carte à puce

Vient maintenant la partie cruciale : accéder au certificat numérique stocké sur votre carte à puce. Voici comment procéder :

### Ouvrir le magasin de certificats

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
Nous ouvrons le magasin de certificats situé dans le profil de l'utilisateur actuel. Cela nous permet d'accéder aux certificats installés sur votre machine, y compris ceux de votre carte à puce.

### Sélectionnez le certificat

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
Ce code invite l'utilisateur à sélectionner un certificat dans la collection. L'interface utilisateur affiche tous les certificats disponibles, vous permettant de choisir celui associé à votre carte à puce.

## Étape 4 : Créer la signature externe

Une fois que vous avez sélectionné votre certificat, l’étape suivante consiste à créer une signature externe en utilisant le certificat sélectionné.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
Ici, nous créons une instance de`ExternalSignature` en utilisant le certificat sélectionné. Cet objet sera utilisé pour signer le document PDF.

## Étape 5 : Définir l’apparence de la signature

Maintenant, définissons l'apparence de notre signature. C'est ici que vous pouvez personnaliser l'apparence de votre signature sur le document.

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
 Dans cet extrait, nous spécifions l'apparence de la signature en fournissant le chemin d'accès à un fichier image (comme un logo ou un graphique de signature). Assurez-vous de remplacer`"demo.png"` avec l'image réelle que vous souhaitez utiliser.

## Étape 6 : Signez le PDF

Une fois tout mis en place, il est temps de signer le document PDF !

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
Dans cette étape, nous appelons le`Sign` méthode sur notre`pdfSign` objet. Voici la signification de chaque paramètre :
- `1`:Le numéro de page où la signature apparaîtra.
- `"Reason"`:La raison de la signature du document.
- `"Contact"`:Coordonnées du signataire.
- `"Location"`:L'emplacement du signataire.
- `true`: Indique s'il faut créer une signature visible.
- `new System.Drawing.Rectangle(100, 100, 200, 200)`:La position et la taille de la signature sur le PDF.
- `externalSignature`:L'objet signature que nous avons créé plus tôt.

 Enfin, nous enregistrons le document signé sous`externalSignature2.pdf`.

## Étape 7 : Vérifiez la signature

Après avoir signé le document, il est essentiel de vérifier que la signature est valide. Voici comment procéder :

### Initialiser le processus de vérification

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
 Nous créons une nouvelle instance de`PdfFileSignature` pour le document signé. Nous récupérons ensuite les noms de toutes les signatures présentes dans le document.

### Vérifier la validité de la signature

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
Nous parcourons chaque nom de signature et vérifions sa validité. Si une signature échoue à la vérification, une exception est levée, indiquant que la signature n'est pas valide.

## Conclusion

Et voilà ! Vous avez signé avec succès un document PDF à l'aide d'une carte à puce avec Aspose.PDF pour .NET. Ce processus sécurise non seulement votre document, mais ajoute également une couche d'authenticité qui est cruciale dans le monde numérique d'aujourd'hui. Que vous ayez affaire à des contrats, des documents juridiques ou toute information sensible, savoir comment mettre en œuvre des signatures numériques est une compétence précieuse. 

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et convertir des documents PDF dans des applications .NET.

### Ai-je besoin d’une carte à puce pour signer des PDF ?
Bien qu'une carte à puce ne soit pas obligatoire, elle est fortement recommandée pour les signatures numériques sécurisées, car elle offre une couche de sécurité supplémentaire.

### Puis-je utiliser n’importe quel fichier PDF pour signer ?
Oui, vous pouvez utiliser n'importe quel fichier PDF, mais assurez-vous qu'il n'est pas protégé par un mot de passe. Si c'est le cas, vous devrez d'abord le déverrouiller.

### Que faire si je n’ai pas de certificat numérique ?
Vous pouvez obtenir un certificat numérique auprès d’une autorité de certification (CA) de confiance ou utiliser un certificat auto-signé à des fins de test.

### Existe-t-il une version d'essai d'Aspose.PDF disponible ?
 Oui, vous pouvez télécharger une version d'essai gratuite à partir du[Site Web d'Aspose](https://releases.aspose.com/).