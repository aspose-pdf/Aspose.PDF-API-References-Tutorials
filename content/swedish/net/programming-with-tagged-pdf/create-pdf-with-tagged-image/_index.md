---
title: Skapa PDF med taggad bild
linktitle: Skapa PDF med taggad bild
second_title: Aspose.PDF för .NET API-referens
description: Steg för steg guide för att skapa PDF med taggad bild med Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
I den här handledningen kommer vi att ge dig en steg-för-steg-guide om hur du skapar ett PDF-dokument med en taggad bild med Aspose.PDF för .NET. Aspose.PDF är ett kraftfullt bibliotek som låter dig skapa, manipulera och konvertera PDF-dokument programmatiskt. Med hjälp av de taggade innehållsstrukturfunktionerna i Aspose.PDF kan du lägga till taggade bilder till ditt PDF-dokument.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

1. Visual Studio installerat med .NET framework.
2. Aspose.PDF-biblioteket för .NET.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt projekt i Visual Studio och lägg till en referens till Aspose.PDF för .NET-biblioteket. Du kan ladda ner biblioteket från Asposes officiella webbplats och installera det på din maskin.

## Steg 2: Importera de nödvändiga namnrymden

I din C#-kodfil, importera de namnutrymmen som krävs för att komma åt klasserna och metoderna som tillhandahålls av Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Steg 3: Skapa PDF-dokumentet med en taggad bild

Använd följande kod för att skapa ett PDF-dokument med en taggad bild:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Denna kod skapar ett tomt PDF-dokument och lägger till en taggad bild med metoderna som tillhandahålls av Aspose.PDF. Bilden anges med alt-text, titel och tagg.

## Steg 4: Spara PDF-dokumentet

Använd följande kod för att spara PDF-dokumentet:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Denna kod sparar PDF-dokumentet med den taggade bilden till en angiven fil.

### Exempel på källkod för Skapa PDF med taggad bild med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Lägg till bild med upplösning 300 DPI (som standard)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Spara PDF-dokument
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Slutsats

I den här handledningen lärde du dig hur du skapar ett PDF-dokument med en taggad bild med Aspose.PDF för .NET. Taggade bilder lägger till ytterligare, strukturerad information till ditt PDF-dokument.

### FAQ's

#### F: Vad är syftet med att skapa ett PDF-dokument med en taggad bild med Aspose.PDF för .NET?

S: Genom att skapa ett PDF-dokument med en taggad bild med Aspose.PDF för .NET kan du lägga till taggade bilder till dokumentets innehåll. Taggade bilder ger strukturerad information, såsom alt-text och titlar, vilket förbättrar tillgängligheten och organisationen.

#### F: Hur hjälper Aspose.PDF-biblioteket att skapa ett PDF-dokument med en taggad bild?

S: Aspose.PDF för .NET är ett robust bibliotek som tillhandahåller funktioner för att skapa, manipulera och konvertera PDF-dokument programmatiskt. I den här handledningen används bibliotekets märkta innehållsstrukturfunktioner för att lägga till en märkt bild till PDF-dokumentet.

#### F: Vilka är förutsättningarna för att skapa ett PDF-dokument med en taggad bild med Aspose.PDF för .NET?

S: Innan du börjar, se till att du har Visual Studio installerat med .NET-ramverket och att Aspose.PDF-biblioteket för .NET refereras till i ditt projekt.

#### F: Hur skapar den medföljande C#-koden ett PDF-dokument med en taggad bild?

S: Koden visar hur man skapar ett PDF-dokument, definierar ett taggat bildelement och lägger till det i dokumentets innehåll. Den taggade bilden innehåller alt-text, en titel och en tagg med metoder som tillhandahålls av Aspose.PDF.

#### F: Kan jag använda olika bildformat för den taggade bilden?

S: Ja, du kan använda olika bildformat för den taggade bilden, såsom JPEG, PNG, GIF, etc. Kodexemplet i handledningen använder en JPEG-bild, men du kan ersätta den med sökvägen till en bildfil i ditt föredragna format.

#### F: Hur används den alternativa texten (alt-texten) i taggade bilder?

 S: Alt text ger en textbeskrivning av bilden, som läses upp av skärmläsare för synskadade användare. I den medföljande koden ställs alt-texten in med hjälp av`AlternativeText` egendom av`IllustrationElement` representerar den taggade bilden.

####  F: Hur fungerar`SetTitle` method contribute to the PDF document's tagged image?

 A: Den`SetTitle` metod anger titeln på PDF-dokumentets taggade innehåll, vilket ger ytterligare sammanhang för den taggade bilden. Den här titeln kan hjälpa till att identifiera syftet med eller ämnet för det taggade innehållet.

#### F: Kan jag anpassa taggen och titeln på den taggade bilden?

 S: Ja, du kan anpassa taggen och titeln på den taggade bilden med hjälp av`SetTag` och`Title` metoder för`IllustrationElement`. Kodexemplet visar hur du ställer in taggen till "Fig" och titeln till "Bild 1."

#### F: Hur kan jag säkerställa att den taggade bilden är tillgänglig och överensstämmer med tillgänglighetsstandarder?

S: Genom att använda de taggade innehållsstrukturfunktionerna i Aspose.PDF och tillhandahålla alt-text och annan relevant information bidrar du till den taggade bildens tillgänglighet. Att säkerställa efterlevnad av tillgänglighetsstandarder innebär att man följer bästa praxis för alternativ text och dokumentstruktur.

#### F: Är det möjligt att lägga till flera taggade bilder till samma PDF-dokument med liknande tekniker?

 S: Ja, du kan lägga till flera taggade bilder till samma PDF-dokument med liknande tekniker. Du skulle skapa ytterligare`IllustrationElement` instanser för varje taggad bild och anpassa deras egenskaper efter behov.