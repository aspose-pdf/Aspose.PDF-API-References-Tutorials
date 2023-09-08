---
title: Osynlig anteckning i PDF-fil
linktitle: Osynlig anteckning i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du gör osynliga kommentarer i PDF-fil med C#-källkod med Aspose.PDF för .NET. Steg-för-steg guide.
type: docs
weight: 100
url: /sv/net/annotations/invisibleannotation/
---
Anteckningar i PDF-fil är en kraftfull funktion som låter dig lägga till extra information eller anteckningar till ett dokument utan att ändra det faktiska innehållet. De kan användas för att markera text, uppmärksamma specifika delar av ett dokument eller lägga till kommentarer eller feedback.

Det finns många olika typer av kommentarer som du kan använda i PDF-dokument, inklusive:

- Textanteckningar
- Länkkommentarer
- Stämpelkommentarer
- Ljudkommentarer
- Anteckningar för bifogade filer
- och många fler

## Steg 1: Skapa en osynlig anteckning i ett PDF-dokument med Aspose.PDF för .NET

 För att skapa en osynlig anteckning i ett PDF-dokument med Aspose.PDF för .NET måste vi först skapa en`FreeTextAnnotation` objekt och ange platsen och storleken på anteckningen.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 I koden ovan skapar vi en`FreeTextAnnotation`objekt och ange platsen för anteckningen på sidan 2 i PDF-dokumentet. Vi anger också teckensnittstyp, storlek och färg för texten som kommer att visas i anteckningen.

## Steg 2: Lägga till egenskaper till den osynliga anteckningen

Därefter kan vi lägga till några egenskaper till annoteringen, såsom en kantfärg, bakgrundsfärg eller opacitet.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

I koden ovan ställer vi in kantfärgen på annoteringen till röd.

## Steg 3: Ställ in anteckningsflaggor

Efter att vi har skapat anteckningen och ställt in dess egenskaper kan vi specificera anteckningsflaggor. I den här handledningen vill vi att kommentaren ska vara utskrivbar men inte synlig.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Steg 4: Spara det modifierade PDF-dokumentet

Slutligen kan vi spara det modifierade PDF-dokumentet med den nya osynliga anteckningen.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Exempel på källkod för How to Invisible Annotation med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Spara utdatafil
doc.Save(dataDir);
// ExEnd:InvisibleAnnotation
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Slutsats

den här handledningen lärde vi oss hur man skapar en osynlig anteckning i ett PDF-dokument med Aspose.PDF för .NET. Osynliga anteckningar är en användbar funktion när du vill lägga till extra information eller anteckningar till ett dokument utan att visa dem för läsaren. Genom att följa steg-för-steg-guiden och använda den medföljande C#-källkoden kan utvecklare enkelt skapa och anpassa osynliga kommentarer i sina PDF-dokument. Aspose.PDF för .NET tillhandahåller en omfattande uppsättning verktyg för att arbeta med kommentarer, så att du kan förbättra interaktiviteten och användbarheten av dina PDF-filer.

### FAQ's

#### F: Vad är en osynlig anteckning i ett PDF-dokument?

S: En osynlig anteckning i ett PDF-dokument är en anteckning som inte är synlig på sidan men som innehåller ytterligare information eller anteckningar. Det låter dig lägga till kommentarer eller feedback utan att visa dem för läsaren.

#### F: Vilka typer av egenskaper kan läggas till i en osynlig anteckning?

S: Olika egenskaper kan läggas till i en osynlig anteckning, såsom kantfärg, bakgrundsfärg, opacitet, teckensnitt, storlek och färg för texten som kommer att visas.

#### F: Kan jag ställa in olika anteckningsflaggor för en osynlig anteckning?

S: Ja, du kan ställa in olika anteckningsflaggor för en osynlig anteckning, beroende på dina krav. Du kan till exempel göra anteckningen utskrivbar men inte synlig.

#### F: Hur kan jag lägga till en osynlig kommentar på en specifik sida i PDF-dokumentet?

 S: För att lägga till en osynlig anteckning till en specifik sida i PDF-dokumentet måste du skapa en`FreeTextAnnotation` objekt och ange platsen och storleken för anteckningen på den sidan.

#### F: Kan jag ändra egenskaperna hos en befintlig osynlig anteckning i en PDF-fil?

S: Ja, du kan ändra egenskaperna hos en befintlig osynlig anteckning i en PDF-fil med Aspose.PDF för .NET. Du kan ändra teckensnitt, storlek, färg, kantfärg, bakgrundsfärg, opacitet och andra egenskaper för anteckningen.