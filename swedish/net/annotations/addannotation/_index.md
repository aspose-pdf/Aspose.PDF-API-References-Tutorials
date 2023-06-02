---
title: Lägg till anteckning
linktitle: Lägg till anteckning
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till textkommentarer med Aspose.PDF för .NET med den här C#-källkoden. Anpassa dina kommentarer med specifika detaljer och ikoner.
type: docs
weight: 10
url: /sv/net/annotations/addannotation/
---

Att lägga till kommentarer till PDF-dokument är en kraftfull funktion som kan förbättra samarbetet och granskningsprocesser. Aspose.PDF för .NET gör det enkelt att lägga till kommentarer programmatiskt till PDF-dokument med C#. I den här guiden kommer vi att förklara steg-för-steg hur man använder Aspose.PDF för .NET för att lägga till kommentarer till ett PDF-dokument.

## Steg 1: Skapa ett nytt projekt och installera Aspose.PDF för .NET

Innan vi börjar skriva koden för att lägga till kommentarer måste vi skapa ett nytt projekt och installera Aspose.PDF för .NET. För att installera Aspose.PDF för .NET, följ dessa steg:

1. Öppna Visual Studio och skapa ett nytt C#-projekt.
2. Högerklicka på projektet i Solution Explorer och välj "Hantera NuGet-paket".
3. Sök efter "Aspose.PDF" och välj "Installera".

När installationen är klar kan vi börja skriva koden.

## Steg 2: Öppna PDF-dokumentet

Det första steget i att lägga till kommentarer är att öppna PDF-dokumentet. Vi kan använda följande kod för att öppna dokumentet:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

I den här koden anger vi sökvägen till PDF-dokumentet vi vill öppna. Se till att ersätta "DIN DATAKABEL" med den faktiska sökvägen till din datakatalog.

## Steg 3: Skapa anteckningen

 För att lägga till en anteckning måste vi skapa en ny instans av`TextAnnotation` klass. Vi kan använda följande kod för att skapa en ny textkommentar:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

I den här koden skapar vi en ny textkommentar på den andra sidan av PDF-dokumentet. Vi ställer också in egenskaperna för titel, ämne, status, innehåll, öppen och ikon för annoteringen.

## Steg 4: Anpassa anteckningen

 Vi kan anpassa utseendet på annoteringen med hjälp av`Border` klass. Vi kan använda följande kod för att anpassa gränsen för anteckningen:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 I den här koden skapar vi en ny`Border` objekt och ställ in dess egenskaper för bredd och streck. Vi ställer sedan in`Border` egenskapen för anteckningen till den nya`Border`objekt. Slutligen ställer vi in`Rect` egenskapen för anteckningen för att specificera dess position och storlek.

## Steg 5: Lägg till anteckningen i PDF-dokumentet

När vi har skapat och anpassat anteckningen måste vi lägga till den i PDF-dokumentet. Vi kan använda följande kod för att lägga till kommentaren till PDF-dokumentet:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

I den här koden lägger vi till anteckningen i anteckningssamlingen på den andra sidan av PDF-dokumentet.

## Steg 6: Spara utdatafilen

Slutligen måste vi spara PDF-dokumentet med den tillagda anteckningen. Vi kan använda följande kod för att spara utdatafilen:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Exempel på källkod för att lägga till anteckningar med Aspose.PDF för .NET


```csharp   
 // Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DATA DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Skapa anteckning
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Lägg till anteckningar i anteckningssamlingen på sidan
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Spara utdatafil
pdfDocument.Save(dataDir);
```
Den här koden visar hur man lägger till en textkommentar med en specifik titel, ämne, tillstånd, innehåll och ikon på en PDF-sida med Aspose.PDF för .NET. Du kan ändra den här koden enligt dina krav för att lägga till kommentarer till dina PDF-dokument. Kom bara ihåg att byta ut DIN DATAKABEL med den faktiska katalogsökvägen där din PDF-fil finns och där du vill spara utdatafilen.