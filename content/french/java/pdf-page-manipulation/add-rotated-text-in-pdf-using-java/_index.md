---
title: Ajouter du texte pivoté dans un PDF à l'aide de Java
linktitle: Ajouter du texte pivoté dans un PDF à l'aide de Java
second_title: API de traitement PDF Java Aspose.PDF
description: Découvrez comment insérer du texte pivoté dans un document PDF à l'aide de Java. Suivez ce guide détaillé étape par étape avec des exemples de code pour améliorer vos PDF avec du texte pivoté.
type: docs
weight: 14
url: /fr/java/pdf-page-manipulation/add-rotated-text-in-pdf-using-java/
---

## Introduction

Dans ce didacticiel complet, nous allons nous plonger dans le processus d'ajout de texte pivoté à un document PDF à l'aide de Java. Que vous ayez besoin d'étiqueter des diagrammes, de créer des filigranes ou d'ajouter des effets spéciaux à vos PDF, ce guide vous guidera tout au long des étapes. Nous utiliserons Aspose.PDF pour Java, une puissante bibliothèque de manipulation de PDF, pour illustrer le processus.

## Prérequis

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. Environnement de développement Java : assurez-vous que Java est installé sur votre système.

2.  Aspose.PDF pour Java : Téléchargez et incluez la bibliothèque Aspose.PDF dans votre projet Java. Vous pouvez trouver le lien de téléchargement[ici](https://releases.aspose.com/pdf/java/).

## Étape 1 : Créer un nouveau document PDF

Commençons par créer un nouveau document PDF à l'aide d'Aspose.PDF. Ce document servira de toile pour notre texte pivoté.

```java
// Initialiser le document PDF
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();
```

## Étape 2 : Ajouter une page

Ensuite, ajoutez une page au document PDF où vous souhaitez insérer le texte pivoté :

```java
//Ajouter une nouvelle page au document
com.aspose.pdf.Page page = pdfDocument.getPages().add();
```

## Étape 3 : définir le texte pivoté

Maintenant, définissons le texte que vous souhaitez insérer et faire pivoter. Vous pouvez personnaliser le texte, la police et l'angle de rotation selon vos besoins :

```java
// Définir le contenu du texte
String text = "Rotated Text Example";

// Créer un objet TextFragment
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment(text);

// Définir la taille et le style de la police
textFragment.getTextState().setFontSize(12);
textFragment.getTextState().setFont(com.aspose.pdf.FontRepository.findFont("Arial"));

// Définir l'angle de rotation (en degrés)
textFragment.setTextRotation(45);
```

Dans cet exemple, nous avons défini le texte sur « Exemple de texte pivoté », choisi la police Arial, défini la taille de police sur 12 et fait pivoter le texte de 45 degrés. Ajustez ces paramètres pour qu'ils correspondent à vos besoins spécifiques.

## Étape 4 : Positionnez le texte pivoté

Spécifiez la position sur la page où vous souhaitez placer le texte pivoté :

```java
// Définir la position du texte
textFragment.setPosition(new com.aspose.pdf.Position(100, 200));
```

Ici, nous avons positionné le texte aux coordonnées (100, 200) sur la page. Modifiez ces coordonnées pour placer le texte précisément là où vous en avez besoin.

## Étape 5 : ajouter du texte pivoté à la page

Maintenant, ajoutez le texte pivoté à la page :

```java
// Ajoutez le texte pivoté à la page
page.getParagraphs().add(textFragment);
```

## Étape 6 : Enregistrez le PDF

Enfin, enregistrez le document PDF avec le texte pivoté :

```java
// Enregistrer le document PDF
pdfDocument.save("output.pdf");
```

## Conclusion

Dans ce didacticiel, nous avons exploré le processus d'ajout de texte pivoté à un document PDF à l'aide de Java et d'Aspose.PDF pour Java. Vous avez appris à créer un nouveau PDF, à définir du texte pivoté avec des styles personnalisés, à le positionner sur la page et à enregistrer le PDF modifié.

Le texte pivoté peut être un ajout précieux à vos PDF à diverses fins, telles que l'étiquetage de diagrammes, le filigrane ou l'ajout d'éléments créatifs à vos documents.

Améliorez vos documents PDF en incorporant facilement du texte pivoté, grâce aux fonctionnalités d'Aspose.PDF pour Java.

---

## FAQ (Foire aux questions)

### 1. Puis-je faire pivoter du texte selon différents angles dans le même PDF ?
   Oui, vous pouvez ajouter plusieurs instances de texte pivoté avec des angles différents au même document PDF. Répétez simplement le processus décrit dans ce didacticiel pour chaque élément de texte pivoté.

### 2. Comment puis-je changer la couleur du texte pivoté ?
    Pour changer la couleur du texte, utilisez le`textFragment.getTextState().setForegroundColor` méthode et spécifiez la couleur au format RVB. Par exemple, pour définir la couleur du texte sur rouge, utilisez`textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getRed());`.

### 3. Aspose.PDF pour Java est-elle une bibliothèque gratuite ?
   Aspose.PDF pour Java est une bibliothèque commerciale puissante, mais elle propose une version d'essai gratuite pour les tests et l'évaluation. En fonction des exigences de votre projet, vous pouvez choisir une option de licence appropriée.

### 4. Puis-je faire pivoter le texte de 90 degrés pour créer du texte vertical ?
   Oui, vous pouvez faire pivoter le texte de 90 degrés pour créer un texte vertical. Réglez simplement l'angle de rotation sur 90 degrés et le texte apparaîtra verticalement sur la page.

### 5. Existe-t-il d’autres bibliothèques permettant de travailler avec des PDF en Java ?
   Oui, plusieurs bibliothèques, telles que iText et PDFBox, sont disponibles pour la manipulation de PDF en Java. Chaque bibliothèque possède ses propres fonctionnalités et capacités, alors choisissez celle qui correspond le mieux aux besoins de votre projet.