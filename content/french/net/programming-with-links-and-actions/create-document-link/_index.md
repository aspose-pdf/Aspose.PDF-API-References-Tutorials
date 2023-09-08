---
title: Créer un lien vers un document
linktitle: Créer un lien vers un document
second_title: Aspose.PDF pour la référence de l'API .NET
description: Créez facilement des liens vers d'autres documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-links-and-actions/create-document-link/
---
Créer un lien vers un autre document dans un fichier PDF vous permet de créer des liens cliquables qui redirigent les utilisateurs vers d'autres documents PDF. Avec Aspose.PDF pour .NET, vous pouvez facilement créer de tels liens en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires à votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF auquel vous souhaitez ajouter un lien vers un autre document. Remplacer`"YOUR DOCUMENT DIRECTORY"`dans le code suivant avec le chemin réel de votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF auquel nous souhaitons ajouter le lien vers un autre document en utilisant le code suivant :

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Étape 4 : Créer le lien vers un autre document

 Dans cette étape, nous allons créer le lien vers un autre document en utilisant le`LinkAnnotation` annotation. Nous préciserons les coordonnées et la zone du lien, ainsi que l'action de navigation vers un document externe. Voici le code correspondant :

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Étape 5 : Enregistrez le fichier mis à jour

 Enregistrons maintenant le fichier PDF mis à jour en utilisant le`Save` méthode du`document` objet. Voici le code correspondant :

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Exemple de code source pour créer un lien de document à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Créer un lien
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Enregistrer le document mis à jour
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Conclusion

Félicitation ! Vous disposez désormais d'un guide étape par étape pour créer des liens vers d'autres documents avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour créer des liens cliquables dans vos fichiers PDF, redirigeant les utilisateurs vers d'autres documents.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées des liens interactifs.

### FAQ pour créer un lien vers un document

#### Q : Que sont les liens vers des documents dans les fichiers PDF ?

R : Les liens vers des documents dans les fichiers PDF sont des liens cliquables qui dirigent les utilisateurs vers d'autres documents PDF. Ces liens améliorent la navigation en fournissant un moyen efficace de connecter du contenu connexe et de faciliter une expérience de lecture fluide.

#### Q : Comment puis-je bénéficier de la création de liens vers des documents ?

R : La création de liens vers des documents vous permet d'établir des connexions entre différentes sections ou sujets au sein de vos documents PDF. Cette fonctionnalité permet aux utilisateurs d'accéder facilement à des informations supplémentaires ou à des documents connexes.

#### Q : Comment Aspose.PDF pour .NET prend-il en charge la création de liens vers des documents ?

R : Aspose.PDF pour .NET simplifie le processus de création de liens vers des documents en fournissant un ensemble complet d'API. Le didacticiel étape par étape décrit dans ce guide montre comment ajouter des liens de documents à vos fichiers PDF.

#### Q : Puis-je personnaliser l’apparence des liens vers les documents ?

: Absolument ! Aspose.PDF pour .NET offre des options de personnalisation pour l'apparence des liens de documents, notamment la couleur, le style et les effets de survol. Vous pouvez adapter l'apparence à la conception de votre document.

#### Q : Est-il possible de créer un lien vers des sections ou des pages spécifiques dans un autre document ?

R : Oui, vous pouvez créer des liens qui dirigent les utilisateurs vers des pages ou des sections spécifiques d'un autre document PDF. Aspose.PDF pour .NET offre la flexibilité de définir l'emplacement cible dans le document lié.

#### Q : Comment puis-je m'assurer que les liens vers mes documents sont fonctionnels ?

R : En suivant le didacticiel et l'exemple de code fournis, vous pouvez créer en toute confiance des liens de documents fonctionnels. Vous pouvez tester les liens en ouvrant le document PDF généré et en cliquant sur les liens.

#### Q : Puis-je créer plusieurs liens vers des documents dans un seul fichier PDF ?

 R : Certainement ! Vous pouvez créer plusieurs liens vers des documents dans un seul document PDF à l'aide de l'outil`LinkAnnotation`annotation. Cela vous permet de fournir aux utilisateurs un accès à divers documents connexes à partir de différentes sections.

#### Q : Existe-t-il des limitations lors de la création de liens vers des documents externes ?

R : Lorsque vous créez un lien vers des documents externes, assurez-vous que les documents liés sont accessibles et situés dans les chemins spécifiés. Il est également important de prendre en compte les autorisations des utilisateurs et la compatibilité des documents liés.

#### Q : Puis-je créer des liens vers des documents stockés sur le Web ou dans des référentiels en ligne ?

R : Bien que ce didacticiel se concentre sur les liens vers des documents locaux, Aspose.PDF pour .NET prend également en charge les liens vers des URL Web ou des référentiels en ligne. Vous pouvez adapter le code fourni pour créer des liens vers des documents Web.