---
title: Signer avec une carte à puce en utilisant le champ de signature
linktitle: Signer avec une carte à puce en utilisant le champ de signature
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment signer des PDF en toute sécurité à l'aide d'une carte à puce avec Aspose.PDF pour .NET. Suivez notre guide étape par étape pour une mise en œuvre facile.
type: docs
weight: 120
url: /fr/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
## Introduction

Dans le monde numérique d'aujourd'hui, la sécurisation des documents est plus importante que jamais. Que vous soyez développeur, propriétaire d'entreprise ou simplement une personne qui manipule des informations sensibles, savoir comment signer des PDF électroniquement peut vous faire gagner du temps et garantir l'authentification de vos documents. Dans ce guide, nous vous expliquerons le processus de signature d'un PDF à l'aide d'une carte à puce et d'un champ de signature avec Aspose.PDF pour .NET. 

## Prérequis

Avant de nous plonger dans les détails du processus de signature, assurons-nous que vous disposez de tout ce dont vous avez besoin pour commencer. Voici une liste de contrôle des prérequis :

1. Aspose.PDF pour .NET : Assurez-vous que la bibliothèque Aspose.PDF est installée dans votre environnement .NET. Vous pouvez la télécharger à partir du[site](https://releases.aspose.com/pdf/net/).

2. Visual Studio : vous aurez besoin d'un IDE pour écrire et exécuter votre code .NET. Visual Studio Community Edition est une excellente option gratuite.

3. Une carte à puce : elle est indispensable pour signer votre PDF. Assurez-vous d'avoir un lecteur de carte à puce et les certificats nécessaires installés sur votre machine.

4. Connaissances de base en C# : la familiarité avec la programmation C# vous aidera à comprendre les extraits de code que nous utiliserons.

5. Exemple de document PDF : préparez un exemple de document PDF pour le test. Vous pouvez créer un PDF vierge ou utiliser un PDF existant.

## Paquets d'importation

Avant de commencer à coder, importons les packages nécessaires. Vous devrez inclure les espaces de noms suivants dans votre fichier C# :

```csharp
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Ces espaces de noms vous donneront accès aux classes et méthodes nécessaires pour travailler avec des PDF et gérer les signatures numériques.

## Guide étape par étape pour signer un PDF avec une carte à puce

Maintenant que nous avons défini les prérequis, décomposons le processus de signature en étapes faciles à gérer. Nous passerons en revue chaque étape en détail, pour nous assurer que vous comprenez ce qui se passe en coulisses.

### Étape 1 : Configurez votre répertoire de documents

Que faire : définissez le chemin d’accès à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Explication : Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel où se trouvent vos fichiers PDF. C'est ici que nous lirons le PDF vierge et enregistrerons le document signé.

### Étape 2 : Copiez le PDF vierge

Que faire : créez une copie de votre PDF vierge avec laquelle travailler.

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
```

 Explication : Cette ligne copie le`blank.pdf`fichier vers un nouveau fichier nommé`externalSignature1.pdf` . Le`true` le paramètre permet d'écraser si le fichier existe déjà.

### Étape 3 : Ouvrir le document PDF

Que faire : ouvrez le PDF copié pour le lire et l’écrire.

```csharp
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
    using (Document doc = new Document(fs))
    {
        // Les prochaines étapes se dérouleront ici
    }
}
```

 Explication : Nous utilisons un`FileStream` pour ouvrir notre fichier PDF.`Document` La classe d'Aspose.PDF nous permet de manipuler le contenu PDF.

### Étape 4 : Créer un champ de signature

Que faire : définissez un champ de signature dans le PDF où la signature sera placée.

```csharp
SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
```

 Explication : Ici, nous créons un`SignatureField` sur la deuxième page (l'index des pages commence à partir de 1) du PDF.`Rectangle` définit la position et la taille du champ de signature.

### Étape 5 : Accéder au magasin de certificats de cartes à puce

Procédure à suivre : ouvrez le magasin de certificats pour sélectionner votre certificat de carte à puce.

```csharp
X509Store store = new X509Store(StoreLocation.CurrentUser);
store.Open(OpenFlags.ReadOnly);
```

Explication : Nous accédons au magasin de certificats de l'utilisateur actuel. C'est là que sont stockés vos certificats de carte à puce.

### Étape 6 : Sélectionnez le certificat

Que faire : demander à l’utilisateur de sélectionner un certificat dans le magasin.

```csharp
X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
```

Explication : Cette ligne ouvre une boîte de dialogue vous permettant de sélectionner un certificat. Vous pouvez choisir le certificat associé à votre carte à puce.

### Étape 7 : Créer une signature externe

 Que faire : créer une instance de`ExternalSignature` en utilisant le certificat sélectionné.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
{
    Authority = "Me",
    Reason = "Reason",
    ContactInfo = "Contact"
};
```

 Explication : Nous initialisons le`ExternalSignature` avec le certificat sélectionné. Vous pouvez également définir l'autorité, la raison de la signature et les informations de contact.

### Étape 8 : ajouter le champ de signature au document

Que faire : ajouter le champ de signature au document.

```csharp
field1.PartialName = "sig1";
doc.Form.Add(field1, 1);
```

Explication : Nous donnons un nom au champ de signature et l'ajoutons à la première page du document. Cela prépare le PDF pour la signature.

### Étape 9 : Signer le document

Que faire : utilisez la signature externe pour signer le PDF.

```csharp
field1.Sign(externalSignature);
doc.Save();
```

Explication : Cette ligne signe le document à l'aide de la signature externe et enregistre les modifications apportées au PDF. Votre document est désormais signé !

### Étape 10 : Vérifiez la signature

Que faire : Vérifiez si la signature est valide.

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
    for (int index = 0; index <= sigNames.Count - 1; index++)
    {
        if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
        {
            throw new ApplicationException("Not verified");
        }
    }
}
```

Explication : Nous créons une instance de`PdfFileSignature` pour vérifier les signatures dans le document. Si la signature n'est pas valide, une exception est levée.

## Conclusion

Félicitations ! Vous venez d'apprendre à signer un document PDF à l'aide d'une carte à puce et d'un champ de signature avec Aspose.PDF pour .NET. Ce processus sécurise non seulement vos documents, mais garantit également leur authenticité, ce qui en fait une compétence essentielle dans le paysage numérique actuel. Que vous signiez des contrats, des factures ou tout autre document important, savoir comment mettre en œuvre des signatures numériques peut vous faire gagner du temps et vous apporter une tranquillité d'esprit.

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et convertir des documents PDF dans des applications .NET.

### Ai-je besoin d’une carte à puce pour signer des PDF ?
Oui, une carte à puce est nécessaire pour signer des PDF en toute sécurité avec un certificat numérique.

### Puis-je utiliser Aspose.PDF gratuitement ?
 Aspose.PDF propose un essai gratuit, que vous pouvez télécharger[ici](https://releases.aspose.com/).

### Comment puis-je vérifier un PDF signé ?
 Vous pouvez utiliser le`PdfFileSignature` classe dans Aspose.PDF pour vérifier les signatures dans votre document PDF.

### Où puis-je trouver plus de documentation sur Aspose.PDF ?
 Vous pouvez vérifier le[Documentation Aspose.PDF](https://reference.aspose.com/pdf/net/) pour plus de détails et d'exemples.