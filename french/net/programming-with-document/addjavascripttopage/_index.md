---
title: Ajouter un script Java au fichier PDF
linktitle: Ajouter un fichier PDF Java Script
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter JavaScript au fichier PDF en utilisant Aspose.PDF pour .NET. Guide étape par étape avec des didacticiels de code pour la création de scripts au niveau du document et de la page.
type: docs
weight: 10
url: /fr/net/programming-with-document/addjavascripttopage/
---
Pour ajouter JavaScript à un fichier PDF, nous utiliserons Aspose.PDF pour .NET. Cette bibliothèque offre un moyen simple et efficace de travailler avec des fichiers PDF dans des applications .NET. Les étapes suivantes vous guideront tout au long du processus d'ajout de JavaScript à un fichier PDF à l'aide d'Aspose.PDF pour .NET.

## Étape 1 : Chargez le fichier PDF

 La première étape consiste à charger le fichier PDF auquel vous souhaitez ajouter JavaScript. Vous pouvez le faire en utilisant le`Document` classe fournie par Aspose.PDF pour .NET. Le`Document` fournit des méthodes pour charger, enregistrer et manipuler des fichiers PDF.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger un fichier PDF existant
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 2 : Ajouter JavaScript au niveau du document

Pour ajouter du JavaScript au niveau du document, nous utiliserons le`JavascriptAction` classe fournie par Aspose.PDF pour .NET. Cette classe vous permet de spécifier l'instruction JavaScript que vous souhaitez ajouter au fichier PDF.

```csharp
// Ajout de JavaScript au niveau du document
// Instanciez JavascriptAction avec l'instruction JavaScript souhaitée
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Attribuez l'objet JavascriptAction à l'action souhaitée du document
doc.OpenAction = javaScript;
```

Dans ce didacticiel, nous ajoutons une instruction JavaScript qui imprimera le fichier PDF avec les options spécifiées lors de l'ouverture du document.

## Étape 3 : Ajouter JavaScript au niveau de la page

 Pour ajouter du JavaScript au niveau de la page, nous utiliserons le`JavascriptAction` classe et la`Actions` propriété fournie par Aspose.PDF pour .NET. Cette propriété vous permet de spécifier des instructions JavaScript qui seront exécutées lors de l'ouverture ou de la fermeture de la page.

```csharp
// Ajout de JavaScript au niveau de la page
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

Dans ce didacticiel, nous ajoutons des instructions JavaScript qui afficheront un message d'alerte lorsque la page sera ouverte ou fermée.

## Étape 4 : Enregistrer le fichier PDF

Après avoir ajouté le JavaScript au fichier PDF, vous devez enregistrer le fichier modifié. Vous pouvez le faire en utilisant le`Save` méthode proposée par le`Document` classe.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Ce code enregistrera le fichier PDF modifié dans le répertoire spécifié.

### Exemple de code source pour Ajouter un script Java à la page à l'aide d'Aspose.PDF pour .NET

```csharp
            
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger un fichier PDF existant
Document doc = new Document(dataDir + "input.pdf");

// Ajout de JavaScript au niveau du document
// Instanciez JavascriptAction avec l'instruction JavaScript souhaitée
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Attribuez l'objet JavascriptAction à l'action souhaitée du document
doc.OpenAction = javaScript;

// Ajout de JavaScript au niveau de la page
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Conclusion

Dans cet article, nous avons expliqué comment ajouter JavaScript à un fichier PDF au niveau du document et au niveau de la page en utilisant Aspose.PDF pour .NET. Nous avons fourni des instructions étape par étape et inclus le code source complet pour chaque exemple. Grâce à ces connaissances, vous pouvez ajouter JavaScript à vos fichiers PDF et personnaliser leur comportement en fonction de vos besoins.


### FAQ pour ajouter un script java au fichier PDF

#### Q : Qu'est-ce qu'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers PDF dans des applications .NET. Il fournit un large éventail de fonctionnalités pour créer, modifier et manipuler des documents PDF.

#### Q : Puis-je ajouter JavaScript à un document PDF à l'aide d'Aspose.PDF pour .NET ?

R : Oui, Aspose.PDF pour .NET vous permet d'ajouter JavaScript au niveau du document et au niveau de la page d'un fichier PDF, ce qui vous permet de créer des documents PDF dynamiques et interactifs.

#### Q : Comment charger un fichier PDF existant à l'aide d'Aspose.PDF pour .NET ?

 R : Vous pouvez charger un fichier PDF existant à l'aide du`Document` classe et ses méthodes, comme indiqué dans le guide étape par étape.

#### Q : Quels types d'actions JavaScript puis-je ajouter à un document PDF ?

R : Avec Aspose.PDF pour .NET, vous pouvez ajouter une grande variété d'actions JavaScript, telles que l'impression, les messages d'alerte, la manipulation de champs de formulaire, etc.

#### Q : Aspose.PDF pour .NET est-il adapté aux projets commerciaux ?

R : Oui, Aspose.PDF pour .NET est une bibliothèque fiable et robuste qui est couramment utilisée dans les projets commerciaux pour les tâches de manipulation et de génération de PDF.

