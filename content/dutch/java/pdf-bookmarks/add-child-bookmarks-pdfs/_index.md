---
title: Voeg onderliggende bladwijzers toe aan PDF's
linktitle: Voeg onderliggende bladwijzers toe aan PDF's
second_title: Aspose.PDF Java PDF-verwerkings-API
description: Leer hoe u PDF-documenten kunt verbeteren met onderliggende bladwijzers met behulp van Aspose.PDF voor Java. Stapsgewijze handleiding met codevoorbeelden voor verbeterde navigatie en organisatie.
type: docs
weight: 11
url: /nl/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Inleiding tot het toevoegen van onderliggende bladwijzers aan PDF's

In dit artikel zullen we onderzoeken hoe u onderliggende bladwijzers aan PDF-documenten kunt toevoegen met behulp van Aspose.PDF voor Java. Onderliggende bladwijzers zijn een handige manier om de inhoud van een PDF-document te ordenen en er doorheen te navigeren, waardoor gebruikers gemakkelijker specifieke secties of onderwerpen in het document kunnen vinden.

## Vereisten

Voordat we ingaan op de implementatie, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java-ontwikkelomgeving op uw systeem geïnstalleerd.
-  Aspose.PDF voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/pdf/java/).

## De omgeving instellen

1. Download de Aspose.PDF voor Java-bibliotheek via de meegeleverde link.
2. Voeg de bibliotheek toe aan uw Java-project.

Laten we nu beginnen met het maken van een nieuw PDF-document en stap voor stap onderliggende bladwijzers eraan toevoegen.

## Een nieuw PDF-document maken

Om te beginnen moeten we een PDF-document initialiseren en er pagina's aan toevoegen. Hier is het codefragment om aan de slag te gaan:

```java
// Initialiseer een PDF-document
Document pdfDocument = new Document();

// Voeg pagina's toe aan de PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

In dit voorbeeld hebben we een nieuw PDF-document gemaakt en er twee pagina's aan toegevoegd.

## Bovenliggende bladwijzers toevoegen

Bovenliggende bladwijzers dienen als de hoofdsecties of categorieën in uw PDF-document. Laten we enkele bovenliggende bladwijzers maken:

```java
// Maak bovenliggende bladwijzers
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

We hebben twee bovenliggende bladwijzers toegevoegd: 'Ouderbladwijzer 1' en 'Ouderbladwijzer 2'.

## Onderliggende bladwijzers toevoegen

Nu is het tijd om onderliggende bladwijzers toe te voegen aan de bovenliggende bladwijzers die we eerder hebben gemaakt. Onderliggende bladwijzers vertegenwoordigen specifieke onderwerpen of subsecties binnen elke bovenliggende bladwijzer. Hier ziet u hoe u het kunt doen:

```java
// Onderliggende bladwijzers toevoegen aan bovenliggende bladwijzer 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Voeg onderliggende bladwijzers toe aan bovenliggende bladwijzer 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

We hebben onderliggende bladwijzers toegevoegd aan zowel 'Ouderbladwijzer 1' als 'Ouderbladwijzer 2'.

## Het uiterlijk van bladwijzers aanpassen

U kunt het uiterlijk van bladwijzers aanpassen door de tekst en stijl ervan te wijzigen. Bovendien kunt u pictogrammen aan bladwijzers toevoegen voor een betere visuele weergave. Hier is een voorbeeld van hoe u dit moet doen:

```java
// Pas het uiterlijk van de bladwijzer aan
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

In dit voorbeeld hebben we de bovenliggende bladwijzer cursief gemaakt, de tekstkleur van de onderliggende bladwijzer gewijzigd in groen en een cursief pictogram aan de onderliggende bladwijzer toegevoegd.

## Gebeurtenissen afhandelen

Aan bladwijzers kunnen ook acties zijn gekoppeld. U kunt bijvoorbeeld acties toevoegen die worden geactiveerd wanneer een gebruiker op een bladwijzer klikt. Zo kunt u klikgebeurtenissen voor bladwijzers verwerken:

```java
// Voeg een actie toe aan een bladwijzer
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

In deze code hebben we een actie 'GoTo' toegevoegd aan een onderliggende bladwijzer, waardoor de gebruiker naar de tweede pagina van de pdf wordt geleid wanneer erop wordt geklikt.

## De PDF opslaan

Nadat u alle benodigde bladwijzers heeft toegevoegd en hun uiterlijk en acties heeft aangepast, kunt u het gewijzigde PDF-document opslaan:

```java
// Sla het PDF-document op
pdfDocument.save("output.pdf");
```

Uw PDF-document met onderliggende bladwijzers is nu klaar.

## Volledige broncode

Hier is de volledige broncode voor het toevoegen van onderliggende bladwijzers aan een PDF-document met Aspose.PDF voor Java:

```java
// Initialiseer een PDF-document
Document pdfDocument = new Document();

// Voeg pagina's toe aan de PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Maak bovenliggende bladwijzers
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Onderliggende bladwijzers toevoegen aan bovenliggende bladwijzer 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Voeg onderliggende bladwijzers toe aan bovenliggende bladwijzer 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Pas het uiterlijk van de bladwijzer aan
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Voeg een actie toe aan een bladwijzer
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Sla het PDF-document op
pdfDocument.save("output.pdf");
```

## Conclusie

Het toevoegen van onderliggende bladwijzers aan PDF's met Aspose.PDF voor Java is een krachtige functie die de navigatie en organisatie van uw documenten verbetert. Door de stappen in dit artikel te volgen, kunt u goed gestructureerde PDF's maken met bovenliggende en onderliggende bladwijzers, het uiterlijk ervan aanpassen en zelfs acties toevoegen om de gebruikerservaring te verbeteren.

## Veelgestelde vragen

### Hoe kan ik Aspose.PDF voor Java downloaden?

 U kunt Aspose.PDF voor Java downloaden van de website[hier](https://releases.aspose.com/pdf/java/).

### Worden onderliggende bladwijzers ondersteund in alle PDF-viewers?

Ja, onderliggende bladwijzers worden ondersteund in de meeste moderne PDF-viewers en bieden een verbeterde gebruikerservaring bij het navigeren door PDF-documenten.

### Kan ik het uiterlijk van bladwijzers verder aanpassen?

Ja, u kunt het uiterlijk van bladwijzers aanpassen door tekststijlen, kleuren en pictogrammen aan te passen aan het ontwerp van uw document.

### Welke andere acties kan ik toevoegen aan bladwijzers?

Naast "GoTo"-acties kunt u acties toevoegen zoals "URI"-acties om weblinks te openen of "JavaScript"-acties om aangepaste scripts uit te voeren wanneer op een bladwijzer wordt geklikt.

### Is Aspose.PDF voor Java geschikt voor commerciële projecten?

Ja, Aspose.PDF voor Java is geschikt voor zowel persoonlijke als commerciële projecten en biedt een breed scala aan functies voor het manipuleren en genereren van PDF's.