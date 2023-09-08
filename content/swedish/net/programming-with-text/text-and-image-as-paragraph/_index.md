---
title: Text Och Bild Som Stycke I PDF-fil
linktitle: Text Och Bild Som Stycke I PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till text och en bild som inline-stycken i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 530
url: /sv/net/programming-with-text/text-and-image-as-paragraph/
---
Denna handledning förklarar hur man lägger till text och en bild som inline-stycken i PDF-fil med Aspose.PDF för .NET. Den medföljande C#-källkoden demonstrerar processen steg för steg.

## Förutsättningar

Innan du fortsätter med handledningen, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller använda NuGet för att installera det i ditt projekt.

## Steg 1: Konfigurera projektet

Börja med att skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnutrymmen

Lägg till följande med hjälp av direktiv i början av din C#-fil för att importera de nödvändiga namnrymden:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Steg 3: Ställ in sökvägen till dokumentkatalogen

 Ställ in sökvägen till din dokumentkatalog med hjälp av`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Skapa ett nytt dokument och sida

 Skapa en ny`Document` objekt och lägg till en sida i dess sidsamling:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Steg 5: Skapa ett TextFragment och lägg till det som ett stycke

 Skapa en`TextFragment` objekt och lägg till det i styckesamlingen på sidan:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Steg 6: Lägg till en bild som ett inline-stycke

 Skapa en`Aspose.Pdf.Image` objekt och ställ in det som ett inline-stycke så att det visas precis efter föregående stycke:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Valfritt: Ställ in bildhöjd
image.FixWidth = 100; // Valfritt: Ställ in bildbredd
page.Paragraphs.Add(image);
```

 Byta ut`"aspose-logo.jpg"` med det faktiska bildfilens namn och justera den valfria bildens höjd och bredd efter önskemål.

## Steg 7: Lägg till ytterligare ett TextFragment som ett inline-stycke

 Återinitiera`TextFragment` objekt med annat innehåll och lägg till det som ett inline-stycke:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Steg 8: Spara PDF-dokumentet

Spara det ändrade PDF-dokumentet:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Se till att byta ut`"TextAndImageAsParagraph_out.pdf"` med önskat utdatafilnamn.

### Exempel på källkod för text och bild som stycke med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiera dokumentinstans
Document doc = new Document();
// Lägg till sida till sidsamling av dokumentinstans
Page page = doc.Pages.Add();
// Skapa TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Lägg till textfragment till styckesamlingen av sidobjekt
page.Paragraphs.Add(text);
// Skapa en bildinstans
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Ställ in bilden som inline-stycke så att den visas direkt efter
// Föregående styckeobjekt (TextFragment)
image.IsInLineParagraph = true;
// Ange sökväg till bildfilen
image.File = dataDir + "aspose-logo.jpg";
// Ställ in bildhöjd (valfritt)
image.FixHeight = 30;
// Ställ in bildbredd (valfritt)
image.FixWidth = 100;
// Lägg till bild till styckesamling av sidobjekt
page.Paragraphs.Add(image);
// Återinitiera TextFragment-objekt med olika innehåll
text = new TextFragment(" Hello Again..");
// Ställ in TextFragment som inline-stycke
text.IsInLineParagraph = true;
// Lägg till nyskapade TextFragment till styckesamlingen på sidan
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du lägger till text och en bild som inline-stycken i ett PDF-dokument med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att ställa in projektet till att spara det ändrade dokumentet. Du kan nu infoga den här koden i dina egna C#-projekt för att anpassa layouten för text och bilder i PDF-filer.

### FAQ's

#### F: Vad är syftet med handledningen "Text och bild som stycke i PDF-fil"?

S: Handledningen "Text och bild som stycke i PDF-fil" syftar till att vägleda användare om hur man lägger till både text och bilder som inline-stycken i ett PDF-dokument med Aspose.PDF för .NET. Handledningen innehåller steg-för-steg-instruktioner och C#-kodexempel för att demonstrera processen.

#### F: Hur hjälper den här handledningen att lägga till text och bilder som inline-stycken?

S: Denna handledning hjälper användare att förstå hur man använder Aspose.PDF för .NET för att infoga både text och bilder som inline-stycken i ett PDF-dokument. Genom att följa stegen och kodexemplen kan användare skapa PDF-filer med anpassade layouter som kombinerar text och bilder.

#### F: Vilka förutsättningar krävs för att följa denna handledning?

S: Innan du startar handledningen bör du ha en grundläggande förståelse för programmeringsspråket C#. Dessutom måste du ha Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller installera det i ditt projekt med NuGet.

#### F: Hur ställer jag in mitt projekt för att följa denna handledning?

S: Till att börja, skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket. Detta gör att du kan använda bibliotekets funktioner för att arbeta med PDF-dokument, textfragment och bilder.

#### F: Kan jag använda den här handledningen för att lägga till flera text- och bildstycken i en PDF?

S: Ja, du kan använda de medföljande kodexemplen för att lägga till flera instanser av både text- och bildstycken i samma PDF-dokument. Den här handledningen visar hur man skapar inline-stycken, vilket gör det enkelt att inkludera olika kombinationer av text och bilder.

#### F: Hur anger jag innehållet och utseendet på textstyckena och bilderna?

 S: Handledningen visar hur man skapar`TextFragment`objekt för att representera textstycken och`Aspose.Pdf.Image` objekt för att representera bilder. Du kan anpassa innehållet, dimensionerna och utseendet på både text och bilder med hjälp av de medföljande kodexemplen.

#### F: Kan jag justera layouten för de infogade styckena?

 S: Ja, du kan justera layouten för inline-stycken genom att kontrollera deras placering, dimensioner och ordning på sidan. Handledningen visar hur man ställer in inline-attribut, som t.ex`IsInLineParagraph`, för att styra layouten för text- och bildstycken.

#### F: Hur sparar jag det ändrade PDF-dokumentet?

 S: För att spara det ändrade PDF-dokumentet kan du använda`Save` metod för`Document` objekt. Handledningen ger kodexempel som visar hur man sparar det resulterande PDF-dokumentet.