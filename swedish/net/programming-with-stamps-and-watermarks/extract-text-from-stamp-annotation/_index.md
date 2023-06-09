---
title: Extrahera text från stämpelkommentar
linktitle: Extrahera text från stämpelkommentar
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du enkelt extraherar text från en stämpelkommentar i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 80
url: /sv/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
den här handledningen tar vi dig steg för steg om hur du extraherar text från en stämpelkommentar i ett PDF-dokument med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att extrahera texten från en specifik stämpelkommentar på en viss sida i PDF-dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Laddar PDF-dokumentet

Det första steget är att ladda det befintliga PDF-dokumentet i ditt projekt. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet
Document doc = new Document(dataDir + "test.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 3: Extrahera text från stämpelkommentaren

Nu när du har laddat PDF-dokumentet kan du extrahera texten från den specifika stämpelkommentaren. Här är hur:

```csharp
// Hämta buffertkommentar
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Skapa en textabsorbent
TextAbsorber ta = new TextAbsorber();

// Besök anteckningens utseende
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Visa den extraherade texten
Console.WriteLine(ta.Text);
```

Koden ovan hämtar stämpelkommentaren från den angivna sidan i PDF-dokumentet och använder sedan en textabsorbent för att extrahera texten från anteckningens utseende. Den extraherade texten visas sedan i utgången.

### Exempel på källkod för att extrahera text från stämpelkommentar med Aspose.PDF för .NET 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## Slutsats

Grattis! Du har lärt dig hur man extraherar text från en stämpelkommentar i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu använda den här metoden för att extrahera text från andra kommentarer i dina PDF-dokument.
