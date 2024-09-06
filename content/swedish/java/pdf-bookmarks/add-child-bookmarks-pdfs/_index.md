---
title: Lägg till underordnade bokmärken till PDF-filer
linktitle: Lägg till underordnade bokmärken till PDF-filer
second_title: Aspose.PDF Java PDF Processing API
description: Lär dig hur du förbättrar PDF-dokument med underordnade bokmärken med Aspose.PDF för Java. Steg-för-steg guide med kodexempel för förbättrad navigering och organisation.
type: docs
weight: 11
url: /sv/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Introduktion till att lägga till underordnade bokmärken till PDF-filer

I den här artikeln kommer vi att utforska hur man lägger till underordnade bokmärken till PDF-dokument med Aspose.PDF för Java. Underordnade bokmärken är ett bekvämt sätt att organisera och navigera genom innehållet i ett PDF-dokument, vilket gör det lättare för användare att hitta specifika avsnitt eller ämnen i dokumentet.

## Förutsättningar

Innan vi dyker in i implementeringen, se till att du har följande förutsättningar på plats:

- Java-utvecklingsmiljö installerad på ditt system.
-  Aspose.PDF för Java-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/pdf/java/).

## Ställa in miljön

1. Ladda ner Aspose.PDF för Java-biblioteket från den medföljande länken.
2. Lägg till biblioteket i ditt Java-projekt.

Låt oss nu börja med att skapa ett nytt PDF-dokument och lägga till underordnade bokmärken till det steg för steg.

## Skapa ett nytt PDF-dokument

För att börja måste vi initiera ett PDF-dokument och lägga till sidor till det. Här är kodavsnittet för att komma igång:

```java
// Initiera ett PDF-dokument
Document pdfDocument = new Document();

// Lägg till sidor i PDF-filen
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

I det här exemplet har vi skapat ett nytt PDF-dokument och lagt till två sidor till det.

## Lägga till föräldrabokmärken

Överordnade bokmärken fungerar som huvudsektioner eller kategorier i ditt PDF-dokument. Låt oss skapa några överordnade bokmärken:

```java
// Skapa överordnade bokmärken
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Vi har lagt till två överordnade bokmärken, "Parent Bookmark 1" och "Parent Bookmark 2."

## Lägga till barnbokmärken

Nu är det dags att lägga till underordnade bokmärken till de överordnade bokmärkena vi skapade tidigare. Underordnade bokmärken representerar specifika ämnen eller underavsnitt inom varje överordnat bokmärke. Så här kan du göra det:

```java
// Lägg till barnbokmärken till föräldrabokmärke 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Lägg till barnbokmärken till föräldrabokmärke 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Vi har lagt till barnbokmärken till både "Föräldrabokmärke 1" och "Föräldrabokmärke 2".

## Anpassa bokmärkes utseende

Du kan anpassa utseendet på bokmärken genom att ändra deras text och stil. Dessutom kan du lägga till ikoner i bokmärken för bättre visuell representation. Här är ett exempel på hur man gör:

```java
// Anpassa bokmärkets utseende
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

I det här exemplet har vi gjort det överordnade bokmärket kursivt, ändrat textfärgen på det underordnade bokmärket till grönt och lagt till en kursiv ikon till det underordnade bokmärket.

## Hantera evenemang

Bokmärken kan också ha åtgärder kopplade till dem. Du kan till exempel lägga till åtgärder som utlöser när en användare klickar på ett bokmärke. Så här kan du hantera bokmärkesklickhändelser:

```java
// Lägg till en åtgärd till ett bokmärke
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

I den här koden har vi lagt till en "Gå till"-åtgärd i ett underordnat bokmärke som tar användaren till den andra sidan i PDF-filen när den klickas.

## Sparar PDF:en

När du har lagt till alla nödvändiga bokmärken och anpassat deras utseende och åtgärder kan du spara det ändrade PDF-dokumentet:

```java
// Spara PDF-dokumentet
pdfDocument.save("output.pdf");
```

Ditt PDF-dokument med underordnade bokmärken är nu klart.

## Komplett källkod

Här är den fullständiga källkoden för att lägga till underordnade bokmärken till ett PDF-dokument med Aspose.PDF för Java:

```java
// Initiera ett PDF-dokument
Document pdfDocument = new Document();

// Lägg till sidor i PDF-filen
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Skapa överordnade bokmärken
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Lägg till barnbokmärken till föräldrabokmärke 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Lägg till barnbokmärken till föräldrabokmärke 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Anpassa bokmärkets utseende
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Lägg till en åtgärd till ett bokmärke
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Spara PDF-dokumentet
pdfDocument.save("output.pdf");
```

## Slutsats

Att lägga till underordnade bokmärken till PDF-filer med Aspose.PDF för Java är en kraftfull funktion som förbättrar navigeringen och organisationen av dina dokument. Genom att följa stegen som beskrivs i den här artikeln kan du skapa välstrukturerade PDF-filer med överordnade och underordnade bokmärken, anpassa deras utseende och till och med lägga till åtgärder för att förbättra användarupplevelsen.

## FAQ's

### Hur kan jag ladda ner Aspose.PDF för Java?

 Du kan ladda ner Aspose.PDF för Java från webbplatsen[här](https://releases.aspose.com/pdf/java/).

### Stöds underordnade bokmärken i alla PDF-läsare?

Ja, underordnade bokmärken stöds i de flesta moderna PDF-läsare och ger en förbättrad användarupplevelse för att navigera genom PDF-dokument.

### Kan jag anpassa utseendet på bokmärken ytterligare?

Ja, du kan anpassa utseendet på bokmärken genom att justera textstilar, färger och ikoner så att de passar ditt dokuments design.

### Vilka andra åtgärder kan jag lägga till i bokmärken?

Förutom "GoTo"-åtgärder kan du lägga till åtgärder som "URI"-åtgärder för att öppna webblänkar eller "JavaScript"-åtgärder för att köra anpassade skript när ett bokmärke klickas.

### Är Aspose.PDF för Java lämplig för kommersiella projekt?

Ja, Aspose.PDF för Java är lämplig för både personliga och kommersiella projekt, och den erbjuder ett brett utbud av funktioner för PDF-manipulering och generering.