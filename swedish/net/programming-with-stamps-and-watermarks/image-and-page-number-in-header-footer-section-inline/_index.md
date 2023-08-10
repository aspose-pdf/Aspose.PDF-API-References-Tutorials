---
title: Bild och sidnummer i sidfotsavsnittet Inline
linktitle: Bild och sidnummer i sidfotsavsnittet Inline
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till bild och sidnummer i sidhuvud och sidfot med hjälp av inline-stycken med Aspose.PDF för .NET.
type: docs
weight: 120
url: /sv/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
den här handledningen guidar vi dig steg för steg om hur du lägger till bild och sidnummer i sidhuvudet och sidfoten i PDF-dokumentet med Aspose.PDF för .NET. Vi kommer att använda den medföljande C#-källkoden för att skapa en sida, ställa in sidhuvud och sidfot, lägga till bild och text med hjälp av inline-stycken i rubriken i PDF-dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Skapa PDF-dokumentet och -sidan

Det första steget är att skapa ett nytt dokumentobjekt och en sida i PDF-dokumentet. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa ett nytt dokumentobjekt
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Skapa en sida i dokumentet
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Koden ovan skapar ett nytt dokumentobjekt och en tom sida i PDF-dokumentet.

## Steg 3: Lägga till rubriken med en bild och inbäddad text

Nu när sidan är skapad kan vi lägga till en rubrik med en bild och text med hjälp av inline-stycken. Här är hur:

```csharp
// Skapa en rubriksektion
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ställ in sidhuvudet
page. Header = header;

// Skapa ett TextFragment-objekt för den första infogade texten
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Ange textfärg
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Skapa ett bildobjekt för bilden
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Ställ in bildsökväg
image1.File = dataDir + "aspose-logo.jpg";

// Definiera bildens mått
image1.FixWidth = 50;
image1.FixHeight = 20;

// Ange att den första infogade texten är en bild
image1.IsInLineParagraph = true;

// Skapa en andra inline-text
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Lägg till objekt i rubriken
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Koden ovan skapar en rubriksektion, ställer in sidhuvudet med denna sektion, lägger till ett TextFragment med infogat text och ett infogat bildobjekt.

## Steg 4: Spara det ändrade PDF-dokumentet

När rubriken med bilden och den infogade texten har lagts till kan vi spara det ändrade PDF-dokumentet. Här är hur:

```csharp
// Spara det ändrade PDF-dokumentet
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Ovanstående kod sparar det redigerade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för bild och sidnummer i sidhuvud Footersection Inline med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera ett dokumentobjekt genom att anropa dess tomma konstruktor
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Skapa en sida i Pdf-objektet
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Skapa rubriksektion för dokumentet
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ställ in rubriken för PDF-filen
page.Header = header;

// Skapa ett textobjekt
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Ange färg
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Skapa ett bildobjekt i avsnittet
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//Ställ in sökvägen till bildfilen
image1.File = dataDir + "aspose-logo.jpg";

// Ställ in information om bildbredden
image1.FixWidth = 50;
image1.FixHeight = 20;

// Ange att seg1s InlineParagraph är en bild.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Spara pdf
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till en bild och sidnummer i sidhuvudet och sidfoten i ett PDF-dokument med hjälp av inline-stycken med Aspose.PDF för .NET. Du kan nu anpassa sidhuvudet och sidfoten på dina PDF-dokument flexibelt.

### FAQ's

#### F: Vad är fördelen med att använda inline-stycken för att lägga till en bild och text i rubriken på ett PDF-dokument?

S: Genom att använda inline-stycken kan du sömlöst integrera bilder och text i samma stycke, vilket ger exakt kontroll över deras placering och formatering. Den här metoden är särskilt användbar för att skapa anpassade rubriker med visuella element.

#### F: Hur uppnår den medföljande C#-källkoden inline-stycken för rubriken i ett PDF-dokument?

S: Den medföljande koden visar hur man skapar ett PDF-dokument, lägger till en sida och anpassar rubriken med hjälp av inline-stycken. Den lägger till ett TextFragment med inbäddad text, en inline-bild och ytterligare ett inline TextFragment.

#### F: Hur anger jag färgen på den infogade texten i rubriken?

 S: Färgen på den infogade texten anges med hjälp av`ForegroundColor` egendom av`TextState` av`TextFragment` objekt.

#### F: Kan jag justera måtten på den infogade bilden i sidhuvudet?

 S: Ja, du kan justera måtten på den infogade bilden med hjälp av`FixWidth` och`FixHeight` egenskaper hos`Image` objekt. Detta gör att du kan styra bildens bredd och höjd i rubriken.

#### F: Kan jag inkludera ytterligare inline-element, som hyperlänkar eller olika teckensnittsstilar, i rubriken?

 S: Ja, du kan inkludera ytterligare inline-element i rubriken genom att skapa fler`TextFragment` eller`Image` objekt med önskade egenskaper. Detta gör att du kan anpassa rubriken ytterligare, inklusive hyperlänkar, olika teckensnittsstilar eller andra visuella element.

#### F: Hur kan jag säkerställa att den infogade bilden och texten förblir korrekt justerade och formaterade på olika enheter och tittare?

S: Aspose.PDF för .NET säkerställer att inline-bilder och text är korrekt justerade och formaterade, vilket resulterar i ett konsekvent utseende på olika enheter och PDF-visare.

#### F: Kan jag tillämpa inline-stycken på sidfotssektionen också?

 S: Ja, du kan använda samma teknik för att använda inline-stycken på sidfotssektionen genom att skapa en`Footer` objekt och lägga till inline-element som text och bilder till det.

#### F: Är det möjligt att kombinera inline-stycken med andra anpassningsmetoder för sidhuvud eller sidfot?

S: Ja, du kan kombinera inline-stycken med andra anpassningsmetoder för sidhuvud eller sidfot som tillhandahålls av Aspose.PDF för .NET för att skapa mer komplexa och skräddarsydda sidhuvuds- eller sidfotsdesigner.

#### F: Kan jag ta bort eller rensa inline-elementen från rubriken om det behövs?

 S: Ja, du kan ta bort eller rensa inline-elementen genom att ändra innehållet i`HeaderFooter` objekt och ta bort respektive infogade stycken.

#### F: Hur kan jag tillämpa inline-stycken på specifika sidor i PDF-dokumentet?

 S: För att tillämpa inline-stycken på specifika sidor kan du skapa separata`HeaderFooter` objekt för varje sida och tilldela dem med hjälp av`Header` respektive egendom`Aspose.Pdf.Page` föremål.