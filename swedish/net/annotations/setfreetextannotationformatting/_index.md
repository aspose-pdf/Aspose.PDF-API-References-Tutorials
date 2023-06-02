---
title: Ställ in formatering av fritextkommentarer
linktitle: Ställ in formatering av fritextkommentarer
second_title: Aspose.PDF för .NET API Referens
description: Den här artikeln ger en steg-för-steg-guide om hur du skapar en fritextkommentar och anger dess innehåll med Aspose.PDF för .NET
type: docs
weight: 140
url: /sv/net/annotations/setfreetextannotationformatting/
---

Aspose.PDF för .NET är ett kraftfullt och lättanvänt API för PDF-dokumentmanipulation som låter dig arbeta med PDF-filer programmatiskt i dina .NET-applikationer. En av funktionerna som tillhandahålls av Aspose.PDF för .NET är möjligheten att ställa in fritextanteckningsformatering i PDF-dokument. I den här artikeln går vi igenom steg-för-steg-processen för att ställa in fritextanteckningsformatering med Aspose.PDF för .NET.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar:

- Microsoft Visual Studio 2010 eller senare
- Aspose.PDF för .NET
- Grundläggande kunskaper i C#



## 1. Skapa en ny C#-konsolapplikation

Skapa först en ny C#-konsolapplikation i Microsoft Visual Studio. För att skapa en ny konsolapplikation, välj "Arkiv" > "Ny" > "Projekt" > "Visuell C#" > "Konsolapplikation" från huvudmenyn.

## 2. Lägg till referens till Aspose.PDF för .NET

Lägg sedan till en referens till Aspose.PDF för .NET i ditt projekt. För att göra detta, högerklicka på ditt projekt i rutan "Solution Explorer", välj "Lägg till" > "Referens" och bläddra sedan till platsen där du sparade Aspose.PDF för .NET DLL-filen. Välj DLL-filen och klicka på "OK" för att lägga till referensen till ditt projekt.

## 3. Ställ in miljön

Efter att ha lagt till referensen till Aspose.PDF för .NET måste du ställa in miljön. För att göra detta, skapa en ny strängvariabel som heter "dataDir" och ställ in den på sökvägen till katalogen där ditt PDF-dokument finns. Ersätt "DIN DOKUMENTKATOLOG" i koden nedan med den faktiska sökvägen till din dokumentkatalog:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4. Öppna PDF-dokumentet

När du har ställt in miljön kan du öppna PDF-dokumentet med följande kod:

```csharp
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Ersätt "SetFreeTextAnnotationFormatting.pdf" med det faktiska namnet på ditt PDF-dokument.

## 5. Ställ in standardutseende

För att ställa in standardutseendet för fritextkommentaren måste du instansiera DefaultAppearance-objektet med önskat teckensnitt, teckenstorlek och färg. I den här handledningen ställer vi in teckensnittet till "Arial", teckenstorleken till 28 och färgen till rött.

```csharp
// Instantiera DefaultAppearance-objekt
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## 6. Skapa en fritextkommentar

Nu när du har ställt in standardutseendet kan du skapa en fritextkommentar med följande kod:

```csharp
// Skapa anteckning
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

Ovanstående kod skapar en ny fritextkommentar på den andra sidan av PDF-dokumentet. Anteckningen kommer att placeras vid (200, 400) och kommer att ha en bredd på 400 och en höjd på 600.

## 7. Ange innehållet i anteckningen

När du har skapat fritextkommentaren kan du ange innehållet i kommentaren med följande kod:

```csharp
// Ange innehållet i anteckningen
freetext.Contents = "Free Text
```

### Exempel på källkod för formatering av fritextkommentarer med Aspose.PDF för .NET
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// Instantiera DefaultAppearance-objekt
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// Skapa anteckning
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// Ange innehållet i anteckningen
freetext.Contents = "Free Text";
// Lägg till anteckningar till anteckningssamlingen på sidan
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// Spara det uppdaterade dokumentet
pdfDocument.Save(dataDir);            
```
