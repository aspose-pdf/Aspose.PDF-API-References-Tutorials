---
title: Ajouter un script Java au fichier PDF
linktitle: Ajouter un fichier PDF Java Script
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter du JavaScript à un fichier PDF à l'aide d'Aspose.PDF pour .NET. Guide étape par étape avec didacticiels de code pour la création de scripts au niveau des documents et des pages.
type: docs
weight: 10
url: /fr/net/programming-with-document/addjavascripttopage/
---
## Introduction

Vous êtes-vous déjà demandé comment améliorer vos PDF avec des éléments interactifs tels que des alertes contextuelles ou des fonctions d'impression automatique ? Eh bien, bonne nouvelle : c'est possible ! En utilisant Aspose.PDF pour .NET, vous pouvez facilement ajouter du JavaScript à vos documents PDF. Que vous automatisiez des tâches ou créiez des expériences utilisateur dynamiques, l'intégration de JavaScript dans les PDF confère à vos fichiers un niveau de fonctionnalité supplémentaire.

## Prérequis

Avant de passer à la partie codage, vous devez configurer quelques éléments :

-  Aspose.PDF pour .NET : Téléchargez la bibliothèque depuis[Sorties d'Aspose](https://releases.aspose.com/pdf/net/) ou obtenir un[essai gratuit](https://releases.aspose.com/).
- Environnement de développement : tout IDE compatible .NET comme Visual Studio.
- Connaissances de base de C# : ce guide suppose que vous êtes familiarisé avec la syntaxe de base de C#.
-  Licence temporaire (facultative) : vous pouvez obtenir une[permis temporaire](https://purchase.aspose.com/temporary-license/) si vous souhaitez éviter les limitations lors de votre développement.

## Paquets d'importation

Avant de commencer à écrire du code, vous devez importer les espaces de noms nécessaires depuis la bibliothèque Aspose.PDF. Ces espaces de noms vous permettront de manipuler des fichiers PDF et d'ajouter facilement des actions JavaScript.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Maintenant que vous avez importé les bons espaces de noms, vous êtes prêt à commencer à coder.

## Étape 1 : charger un PDF existant

Tout d’abord, vous devez charger le document PDF auquel vous souhaitez ajouter du JavaScript. Cette étape prépare le terrain pour toutes les modifications ultérieures. Imaginez que vous disposez d’un PDF que vous souhaitez améliorer avec des fonctionnalités dynamiques, comme l’impression automatique du document à son ouverture.

Voici comment vous pouvez charger ce fichier PDF :

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger un fichier PDF existant
Document doc = new Document(dataDir + "input.pdf");
```

 Dans cet extrait de code, nous utilisons le`Document` classe pour charger un fichier PDF existant à partir du répertoire spécifié. Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre fichier PDF.

## Étape 2 : ajouter du JavaScript au niveau du document

Ajoutons maintenant du JavaScript qui se déclenchera à l'ouverture du document. Dans cet exemple, nous allons écrire un script qui ouvre la boîte de dialogue d'impression dès que l'utilisateur ouvre le PDF.

Le JavaScript au niveau du document est parfait pour les actions que vous souhaitez appliquer à l'ensemble du PDF. Considérez-le comme la configuration d'une règle globale pour votre document.

Voici le code :

```csharp
// Ajout de JavaScript au niveau du document
// Instanciez JavascriptAction avec l'instruction JavaScript souhaitée
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Affecter l'objet JavascriptAction à l'OpenAction du document
doc.OpenAction = javaScript;
```

 Dans cette étape, nous créons un`JavascriptAction` objet qui définit une fonction JavaScript pour ouvrir la boîte de dialogue d'impression lorsque le document est ouvert.`doc.OpenAction` la propriété est ensuite attribuée à cette action JavaScript.

## Étape 3 : ajouter du JavaScript au niveau de la page

Il n'est pas nécessaire que toutes les actions affectent l'intégralité du document. Parfois, vous souhaitez que des actions spécifiques se produisent lorsque certaines pages sont ouvertes ou fermées. Ici, nous allons configurer des actions JavaScript pour l'ouverture et la fermeture d'une page particulière (disons la page 2).

Le JavaScript au niveau de la page est utile pour les interactions ciblées. Il peut s'agir de n'importe quoi, de l'affichage d'un message lorsqu'un utilisateur accède à une page, à des actions personnalisées comme le remplissage automatique des champs de formulaire.

Voici comment procéder :

```csharp
// Ajout de JavaScript au niveau de la page
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

Dans cet extrait de code, nous ajoutons deux actions JavaScript :
1. Action OnOpen : affiche une alerte indiquant « Page 2 ouverte » lorsque l'utilisateur ouvre la page 2.
2. Action OnClose : affiche une alerte indiquant « Page 2 fermée » lorsque l'utilisateur quitte la page 2.

Cela ajoute une couche d'interactivité à votre PDF. Imaginez guider l'utilisateur à travers une série d'étapes sur différentes pages, avec des alertes qui s'affichent lorsqu'il entre ou sort d'une page.

## Étape 4 : Enregistrez le document PDF

Vous avez maintenant ajouté du JavaScript au document et aux pages spécifiques. L'étape finale consiste à enregistrer le PDF modifié à l'emplacement souhaité. Cette partie est simple mais cruciale : n'oubliez pas d'enregistrer votre travail !

Voici le code :

```csharp
// Spécifiez le chemin du fichier de sortie
dataDir = dataDir + "JavaScript-Added_out.pdf";

// Enregistrer le document PDF mis à jour
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

 Dans cet extrait, nous enregistrons le document mis à jour avec le JavaScript ajouté dans un nouveau fichier nommé`"JavaScript-Added_out.pdf"`Cela garantit que vous n'écraserez pas votre fichier d'origine et vous fournit une sauvegarde avec laquelle travailler.

## Conclusion

L'ajout de JavaScript aux fichiers PDF à l'aide d'Aspose.PDF pour .NET est un moyen puissant de créer des PDF interactifs et dynamiques. Que vous automatisiez des tâches telles que l'impression ou la création d'alertes personnalisées, la possibilité d'intégrer JavaScript dans votre PDF rend vos documents plus attrayants et fonctionnels.

## FAQ

### Puis-je ajouter plusieurs actions JavaScript à différentes pages d’un PDF ?
Oui, vous pouvez attribuer différentes actions JavaScript à des pages individuelles ou à l'ensemble du document.

### Est-il possible de supprimer JavaScript d’un PDF après l’avoir ajouté ?
Oui, vous pouvez supprimer ou modifier les actions JavaScript existantes en effaçant le`Actions` propriétés du document ou de la page.

### Quels types de fonctions JavaScript puis-je utiliser dans un PDF ?
Vous pouvez utiliser n'importe quel JavaScript pris en charge par le moteur JavaScript d'Adobe Acrobat, comme l'impression, les alertes et les manipulations de formulaires.

### Le JavaScript fonctionne-t-il dans tous les visualiseurs PDF ?
La plupart des actions JavaScript fonctionnent dans les lecteurs PDF qui prennent en charge les PDF interactifs, comme Adobe Acrobat. Cependant, certains lecteurs PDF de base peuvent ne pas prendre en charge JavaScript.

### Puis-je déclencher des actions JavaScript en fonction de la saisie de l'utilisateur dans le PDF ?
Oui, vous pouvez lier JavaScript aux champs de formulaire pour déclencher des actions en fonction de la saisie de l'utilisateur.