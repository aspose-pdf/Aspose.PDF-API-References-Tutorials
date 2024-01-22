---
title: Textjustering för flytande boxinnehåll i PDF-fil
linktitle: Textjustering för flytande boxinnehåll i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du justerar text i flytande rutor i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 520
url: /sv/net/programming-with-text/text-alignment-for-floating-box-contents/
---
Denna handledning förklarar hur man justerar text i flytande rutor i PDF-fil med Aspose.PDF för .NET. Den medföljande C#-källkoden demonstrerar processen steg för steg.

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
```

## Steg 3: Ställ in sökvägen till dokumentkatalogen

 Ställ in sökvägen till din dokumentkatalog med hjälp av`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Skapa ett nytt dokument

 Skapa en ny`Document` objekt:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## Steg 5: Skapa flytande lådor med textfragment

 Skapa flera`FloatingBox` objekt med olika vertikala och horisontella justeringar:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 Ändra texten och stilen på`TextFragment` föremål som önskas.

## Steg 6: Spara PDF-dokumentet

Spara det ändrade PDF-dokumentet:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 Se till att byta ut`"FloatingBox_alignment_review_out.pdf"` med önskat utdatafilnamn.

### Exempel på källkod för textjustering för flytande boxinnehåll med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du justerar text i flytande rutor i ett PDF-dokument med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att ställa in projektet till att spara det ändrade dokumentet. Du kan nu infoga den här koden i dina egna C#-projekt för att anpassa justeringen av text i flytande rutor i PDF-filer.

### FAQ's

#### F: Vad är syftet med handledningen "Textjustering för flytande boxinnehåll i PDF-fil"?

S: Handledningen "Textjustering för flytande rutor i PDF-fil" syftar till att vägleda användare om hur man justerar text i flytande rutor i ett PDF-dokument med Aspose.PDF för .NET. Handledningen innehåller steg-för-steg-instruktioner och C#-kodexempel för att demonstrera processen.

#### F: Hur hjälper den här handledningen till att justera text i flytande rutor?

S: Denna handledning hjälper användare att förstå hur man använder Aspose.PDF för .NET för att justera text i flytande rutor i ett PDF-dokument. Genom att följa stegen och kodexemplen kan användare anpassa den vertikala och horisontella justeringen av text i flytande rutor.

#### F: Vilka förutsättningar krävs för att följa denna handledning?

S: Innan du startar handledningen bör du ha en grundläggande förståelse för programmeringsspråket C#. Dessutom måste du ha Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller installera det i ditt projekt med NuGet.

#### F: Hur ställer jag in mitt projekt för att följa denna handledning?

S: För att komma igång, skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket. Detta gör att du kan utnyttja bibliotekets funktioner för att arbeta med PDF-dokument och justera text i flytande rutor.

#### F: Kan jag använda den här handledningen för att justera text inom alla typer av flytande rutor?

S: Ja, den här handledningen ger instruktioner om hur man justerar text i flytande rutor i ett PDF-dokument med Aspose.PDF för .NET. Du kan använda de medföljande kodexemplen för att anpassa den vertikala och horisontella justeringen av text i flytande rutor.

#### F: Hur anger jag justeringen av text i en flytande ruta?

 S: Handledningen visar hur man skapar`FloatingBox`föremål och ställ in deras`VerticalAlignment` och`HorizontalAlignment` egenskaper för att styra justeringen av den inneslutna texten. Du kan justera dessa egenskaper efter dina krav.

#### F: Hur kan jag anpassa utseendet på de flytande lådorna?

 S: Du kan anpassa utseendet på de flytande rutorna genom att ändra egenskaper som kant, storlek och textinnehåll. Handledningen ger kodexempel som visar hur man skapar och stilar`FloatingBox` föremål.

#### F: Kan jag lägga till flera flytande rutor med olika justeringar i samma PDF-dokument?

 S: Ja, handledningen illustrerar hur man skapar flera`FloatingBox` objekt med olika vertikala och horisontella justeringar och lägg till dem i samma PDF-dokument. Detta gör att du kan se effekterna av olika justeringar inom samma dokument.

#### F: Hur sparar jag det ändrade PDF-dokumentet?

 S: För att spara det ändrade PDF-dokumentet kan du använda`Save` metod för`Document` objekt. Handledningen ger kodexempel som visar hur man sparar det resulterande PDF-dokumentet.