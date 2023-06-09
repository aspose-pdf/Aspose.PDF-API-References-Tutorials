---
title: Lägg till datum och tidsstämpel
linktitle: Lägg till datum och tidsstämpel
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du enkelt lägger till en datum- och tidsstämpel i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
I den här artikeln tar vi dig steg för steg om hur du lägger till en datum- och tidsstämpel med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att lägga till en datum- och tidsstämpel i ett befintligt PDF-dokument.

## Krav

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 1: Sätta upp miljön

Innan du kan lägga till en datum- och tidsstämpel i ett PDF-dokument måste du konfigurera din utvecklingsmiljö. Här är stegen att följa:

1. Öppna din favorit-IDE (Integrated Development Environment).
2. Skapa ett nytt C#-projekt.
3. Se till att du har lagt till en referens till Aspose.PDF-biblioteket för .NET.

## Steg 2: Lägga till Aspose.PDF-biblioteket

Aspose.PDF-biblioteket för .NET krävs för att arbeta med PDF-dokument i ditt projekt.

## Steg 3: Laddar PDF-dokumentet

Det första steget för att lägga till en datum- och tidsstämpel är att ladda det befintliga PDF-dokumentet i ditt projekt. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 4: Skapa datum- och tidsstämpel

Nu när du har laddat upp dokumentet

  PDF kan du skapa datum- och tidsstämpeln att lägga till. Så här gör du:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Skapa en textbuffert
TextStamp textStamp = new TextStamp(annotationText);
```

Koden ovan skapar en ny textbuffert som innehåller aktuellt datum och tid.

## Steg 5: Konfigurera stämpelegenskaper

Innan du lägger till stämpeln i PDF-dokumentet kan du konfigurera olika egenskaper för stämpeln, såsom marginal, horisontell och vertikal justering, etc. Så här gör du:

```csharp
// Ställ in buffertegenskaper
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Du kan anpassa dessa egenskaper efter dina behov.

## Steg 6: Lägg till stämpel till PDF

Nu när datum- och tidsstämpeln är klar kan du lägga till den på en specifik sida i PDF-dokumentet. Här är hur:

```csharp
// Lägg till frimärket i sidans frimärkssamling
pdfDocument.Pages[1].AddStamp(textStamp);
```

Koden ovan lägger till stämpeln på första sidan i PDF-dokumentet. Du kan ange en annan sida om det behövs.

## Steg 7: Spara utdatadokumentet

När du har lagt till datum- och tidsstämpeln kan du spara det ändrade PDF-dokumentet. Här är hur:

```csharp
// Spara utdatadokumentet
pdfDocument.Save(dataDir);
```

Ovanstående kod sparar det redigerade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för Lägg till datum och tidsstämpel med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Skapa textstämpel
TextStamp textStamp = new TextStamp(annotationText);

// Ställ in egenskaper för stämpeln
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Lägger till stämpel på frimärkssamling
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Spara utdatadokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Slutsats

Grattis! Du har lärt dig hur du lägger till en datum- och tidsstämpel med Aspose.PDF för .NET. Nu kan du tillämpa denna kunskap på dina egna projekt för att lägga till datum- och tidsstämplar till PDF-dokument.
