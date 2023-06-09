---
title: Lägg till PDF-sidastämpel
linktitle: Lägg till PDF-sidastämpel
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du enkelt lägger till en PDF-sidastämpel till dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/programming-with-stamps-and-watermarks/add-pdf-page-stamp/
---

den här handledningen tar vi dig steg för steg om hur du lägger till en PDF-sidastämpel till ett PDF-dokument med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att lägga till en anpassad stämpel på en specifik sida i PDF-dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Laddar PDF-dokumentet

Det första steget är att ladda det befintliga PDF-dokumentet i ditt projekt. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "PDFPageStamp.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 3: Skapa sidbufferten

Nu när du har laddat upp PDF-dokumentet kan du skapa sidstämpeln att lägga till. Så här gör du:

```csharp
// Skapa sidbufferten
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
```

Koden ovan skapar en ny sidbuffert med den första sidan i PDF-dokumentet.

## Steg 4: Konfigurera sidbuffertegenskaper

Innan du lägger till sidstämpeln i PDF-dokumentet kan du konfigurera olika egenskaper för stämpeln, som bakgrund, position, rotation, etc. Så här gör du:

```csharp
// Konfigurera sidbuffertegenskaper
pageStamp. Background = true;
pageStamp. XIndent = 100;
pageStamp. YIndent = 100;
pageStamp.Rotate = Rotate.on180;
```

Du kan anpassa dessa egenskaper efter dina behov.

## Steg 5: Lägga till sidstämpeln i PDF:en

Nu när sidstämpeln är klar kan du lägga till den på en specifik sida i PDF-dokumentet. Här är hur:

```csharp
// Lägg till sidbuffert på specifik sida
pdfDocument.Pages[1].AddStamp(pageStamp);
```

Ovanstående kod lägger till sidstämpeln på första sidan i PDF-dokumentet. Du kan ange en annan sida om det behövs.

## Steg 6: Spara utdatadokumentet

När du har lagt till sidstämpeln kan du spara det ändrade PDF-dokumentet. Här är hur:

```csharp
// Spara utdatadokumentet
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Lägg till PDFPage Stamp med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "PDFPageStamp.pdf");

// Skapa sidstämpel
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
pageStamp.Background = true;
pageStamp.XIndent = 100;
pageStamp.YIndent = 100;
pageStamp.Rotate = Rotation.on180;

// Lägg till stämpel på en viss sida
pdfDocument.Pages[1].AddStamp(pageStamp);
dataDir = dataDir + "PDFPageStamp_out.pdf";

// Spara utdatadokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);

```

Ovanstående kod sparar det redigerade PDF-dokumentet i den angivna katalogen.

## Slutsats

Grattis! Du har lärt dig hur du lägger till en PDF-sidastämpel med Aspose.PDF för .NET. Nu kan du tillämpa denna kunskap på dina egna projekt för att lägga till anpassade stämplar på specifika sidor i dina PDF-dokument.
