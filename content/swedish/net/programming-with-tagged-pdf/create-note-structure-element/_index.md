---
title: Skapa anteckningsstrukturelement
linktitle: Skapa anteckningsstrukturelement
second_title: Aspose.PDF för .NET API-referens
description: Steg-för-steg-guide för att skapa strukturerade anteckningsobjekt i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 30
url: /sv/net/programming-with-tagged-pdf/create-note-structure-element/
---
I den här handledningen kommer vi att ge dig en steg-för-steg-guide om hur du skapar ett anteckningsstrukturelement i ett PDF-dokument med Aspose.PDF för .NET. Aspose.PDF är ett kraftfullt bibliotek som låter dig skapa, manipulera och konvertera PDF-dokument programmatiskt. Med hjälp av de markerade innehållsstrukturfunktionerna i Aspose.PDF kan du lägga till strukturerade anteckningar till ditt PDF-dokument.

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

## Steg 3: Skapa PDF-dokument och anteckningsstrukturerade element

Använd följande kod för att skapa ett PDF-dokument och lägga till strukturerade anteckningselement:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Den här koden skapar ett tomt PDF-dokument och lägger till strukturerade anteckningselement till ett stycke. Varje anteckning skapas med metoderna som tillhandahålls av Aspose.PDF.

## Steg 4: Spara PDF-dokumentet

Använd följande kod för att spara PDF-dokumentet:

```csharp
document. Save(outFile);
```

Denna kod sparar PDF-dokumentet med de strukturerade anteckningselementen till en specificerad fil.

### Exempel på källkod för Skapa anteckningsstrukturelement med Aspose.PDF för .NET 

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Skapa pdf-dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Lägg till styckeelement
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Lägg till NoteElement
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Lägg till NoteElement
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Lägg till NoteElement
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Måste kasta undantag - Aspose.Pdf.Tagged.TaggedException : Strukturelement med ID='note_002' finns redan
//note3.SetId("note_002");
// Det resulterande dokumentet överensstämmer inte med PDF/UA om ClearId() används för Note Structure Element
//note3.ClearId();
// Spara taggat pdf-dokument
document.Save(outFile);
// Kontrollerar PDF/UA-efterlevnad
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Slutsats

I den här handledningen lärde du dig hur du skapar anteckningsstrukturelement i ett PDF-dokument med Aspose.PDF för .NET. Med strukturerade anteckningselement kan du lägga till ytterligare, strukturerad information till ditt PDF-dokument.

### FAQ's

#### F: Vad är syftet med att skapa anteckningsstrukturelement i ett PDF-dokument med Aspose.PDF för .NET?

S: Genom att skapa anteckningsstrukturelement i ett PDF-dokument med Aspose.PDF för .NET kan du lägga till strukturerade anteckningar till dokumentets innehåll. Dessa anteckningar kan ge ytterligare sammanhang, förklaringar eller referenser till specifika delar av innehållet.

#### F: Hur hjälper Aspose.PDF-biblioteket till att skapa anteckningsstrukturelement i ett PDF-dokument?

S: Aspose.PDF för .NET är ett kraftfullt bibliotek som tillhandahåller funktioner för att skapa, manipulera och konvertera PDF-dokument programmatiskt. I denna handledning används bibliotekets markerade innehållsstrukturfunktioner för att skapa strukturerade anteckningselement i PDF-dokumentets innehåll.

#### F: Vilka är förutsättningarna för att skapa anteckningsstrukturelement i ett PDF-dokument med Aspose.PDF för .NET?

S: Innan du börjar, se till att du har Visual Studio installerat med .NET-ramverket och att Aspose.PDF-biblioteket för .NET refereras till i ditt projekt.

#### F: Hur skapar den medföljande C#-koden anteckningsstrukturelement i PDF-dokumentets innehåll?

S: Koden visar hur man skapar ett PDF-dokument, definierar anteckningsstrukturerade element och lägger till dem i ett stycke. Varje anteckning skapas med metoder som tillhandahålls av Aspose.PDF, så att du kan införliva strukturerade anteckningar i innehållet.

#### F: Kan jag anpassa innehållet och egenskaperna för de anteckningsstrukturelement jag skapar?

S: Ja, du kan anpassa innehållet och egenskaperna för anteckningsstrukturelement genom att använda metoderna och egenskaperna som tillhandahålls av Aspose.PDF-biblioteket. Koden visar hur du ställer in text och ID för anteckningselement, men du kan anpassa dem ytterligare efter behov.

#### F: Hur etableras det hierarkiska förhållandet mellan anteckningsstrukturelementen och dokumentets innehåll?

 S: Den hierarkiska relationen upprättas genom att lägga till notstrukturelement som underordnade till andra strukturerade element, såsom stycken. I koden läggs anteckningselement till ett styckeelement med hjälp av`AppendChild` metod.

#### F: Kan jag tilldela unika ID:n till anteckningsstrukturelement?

S: Ja, du kan tilldela unika ID:n till noteringsstrukturelement med hjälp av`SetId` metod. Koden visar hur man ställer in ID:n för anteckningselement till unika värden.

#### F: Vad händer om jag försöker tilldela ett dubblett-ID till ett anteckningsstrukturelement?

S: Ett försök att tilldela ett duplicerat ID till ett anteckningsstrukturelement kommer att resultera i ett undantag. Koden som tillhandahålls i handledningen innehåller en kommentar som illustrerar detta scenario.

#### F: Hur kan jag säkerställa PDF/UA-kompatibilitet när jag skapar anteckningsstrukturelement?

 S: Koden som tillhandahålls i handledningen visar hur man validerar PDF/UA-efterlevnad med hjälp av`Validate` metod. Genom att validera dokumentet mot PDF/UA-standarden kan du säkerställa att de tillagda anteckningsstrukturelementen följer riktlinjerna för tillgänglighet.

#### F: Kan jag använda detta tillvägagångssätt för att lägga till anteckningsstrukturelement till ett befintligt PDF-dokument?

S: Ja, du kan ändra den tillhandahållna metoden för att lägga till anteckningsstrukturelement till ett befintligt PDF-dokument. Istället för att skapa ett nytt dokument skulle du ladda det befintliga dokumentet med Aspose.PDF och sedan följa liknande steg för att lägga till anteckningselement.
