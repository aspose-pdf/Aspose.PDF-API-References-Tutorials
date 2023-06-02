---
title: Osynlig anteckning
linktitle: Osynlig anteckning
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du osynligt kommenterar PDF-filer med C#-källkod med Aspose.PDF för .NET. Steg-för-steg guide.
type: docs
weight: 100
url: /sv/net/annotations/invisibleannotation/
---

Anteckningar i PDF-dokument är en kraftfull funktion som låter dig lägga till extra information eller anteckningar till ett dokument utan att ändra det faktiska innehållet. De kan användas för att markera text, uppmärksamma specifika delar av ett dokument eller lägga till kommentarer eller feedback.

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