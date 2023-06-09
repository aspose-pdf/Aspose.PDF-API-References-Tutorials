---
title: Skapa PDF med taggad bild
linktitle: Skapa PDF med taggad bild
second_title: Aspose.PDF för .NET API Referens
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
