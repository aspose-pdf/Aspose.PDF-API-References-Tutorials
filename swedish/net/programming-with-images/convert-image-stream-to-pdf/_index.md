---
title: Konvertera bildström till PDF
linktitle: Konvertera bildström till PDF
second_title: Aspose.PDF för .NET API Referens
description: Konvertera enkelt en bildström till en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 70
url: /sv/net/programming-with-images/convert-image-stream-to-pdf/
---

Den här guiden tar dig steg för steg hur du konverterar en bildström till en PDF-fil med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Innan du börjar, se till att du ställer in rätt katalog för dokumenten. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där din bild finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Instantiera ett dokumentobjekt

 I detta steg kommer vi att instansiera en`Document` objekt med den tomma konstruktorn för`Aspose.Pdf.Document` klass.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Steg 3: Lägg till en sida i PDF-dokumentet

 Lägg till en sida i PDF-dokumentet med hjälp av`Add` metod för`Pages` föremål för`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Steg 4: Läs bildströmmen

 I detta steg kommer vi att skapa en`FileStream` objekt för att läsa bildfilen från strömmen.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Steg 5: Läs in bilden i en byte-array

 Läs bilden från strömmen och lagra den i en byte-array med hjälp av`Read` metod för`fs` objekt.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Steg 6: Skapa ett MemoryStream-objekt från byte-arrayen

 Skapa en`MemoryStream` objekt från byte-arrayen som innehåller bilden.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Steg 7: Skapa ett bildobjekt

 I detta steg kommer vi att skapa en`Image` objekt med hjälp av`Aspose.Pdf.Image` klass. Ange strömmen för bilden med hjälp av`ImageStream` egendom och passera`ms` objekt vi skapade tidigare.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Steg 8: Lägg till bildobjektet i Paragraphs-samlingen

 Lägg till`imageht` invända mot`Paragraphs` samling av`sec` sektion.

```csharp
sec.Paragraphs.Add(imageht);
```

## Steg 9: Spara PDF-dokumentet

 Spara PDF-dokumentet med hjälp av`Save` metod för`pdf1` objekt. Ange utdatasökvägen för PDF-filen.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Steg 10: Stäng MemoryStream-objektet

 Stäng`ms` objekt med hjälp av`Close` sätt att frigöra resurserna.

```csharp
ms. Close();
```

### Exempel på källkod för Konvertera bildström till PDF med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Instantiera Document-instansen genom att anropa dess tomma konstruktor
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Lägg till en sida i pdf-dokumentet
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Skapa ett FileStream-objekt för att läsa bildfilen
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Läs in bilden i Byte-array
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Skapa ett MemoryStream-objekt från bildbyte-array
MemoryStream ms = new MemoryStream(data);
// Skapa ett bildobjekt
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Ange bildkällan som MemoryStream
imageht.ImageStream = ms;
// Lägg till bildobjekt i paragrafsamlingen i avsnittet
sec.Paragraphs.Add(imageht);
// Spara pdf
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Stäng MemoryStream-objektet
ms.Close();
```

## Slutsats

Grattis! Du har framgångsrikt konverterat en bildström till en PDF-fil med Aspose.PDF för .NET. Den genererade PDF-filen sparas i den angivna katalogen. Du kan nu använda denna PDF-fil i dina projekt eller applikationer.