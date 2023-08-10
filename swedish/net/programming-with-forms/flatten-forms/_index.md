---
title: Platta formulär i PDF-dokument
linktitle: Platta formulär i PDF-dokument
second_title: Aspose.PDF för .NET API Referens
description: Platta enkelt ut formulär i PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 100
url: /sv/net/programming-with-forms/flatten-forms/
---
I den här handledningen kommer vi att visa dig hur du plattar ut formulär med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se först till att du har importerat de nödvändiga biblioteken och ställer in sökvägen till dokumentkatalogen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda käll-PDF-formulär

Ladda käll-PDF-formuläret:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Steg 3: Platta till formerna

Kontrollera först om det finns några formulärfält i dokumentet. Om så är fallet, iterera genom varje fält och tillämpa utjämning:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Steg 4: Spara det uppdaterade dokumentet

Spara det uppdaterade PDF-dokumentet:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Exempel på källkod för Flatten Forms med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda käll-PDF-formulär
Document doc = new Document(dataDir + "input.pdf");
// Platta formulär
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Spara det uppdaterade dokumentet
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Slutsats

I den här handledningen lärde vi oss hur man plattar ut formulär med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt platta till formulär i dina PDF-dokument, göra fält oredigerbara och slå samman kommentarer med dokumentinnehåll.

### FAQ's

#### F: Vad betyder "utplattande formulär" i Aspose.PDF för .NET?

S: Tillplattade formulär i Aspose.PDF för .NET avser processen att göra formulärfält i ett PDF-dokument oredigerbara och sammanfoga kommentarer (som formulärfält, anteckningar och digitala signaturer) med dokumentets innehåll. När formulären väl är tillplattade kan användarna inte ändra formulärfälten och det visuella utseendet på formulärfälten blir en del av det statiska innehållet i PDF-dokumentet.

#### F: Kan jag vända utjämningsprocessen och göra formulärfälten redigerbara igen?

S: Nej, när formulärfälten väl är tillplattade är processen oåterkallelig med Aspose.PDF för .NET. Förplattning sammanfogar permanent formulärfältens utseende med PDF-filens innehåll, och de enskilda formulärfältselementen är inte längre tillgängliga eller redigerbara.

#### F: När ska jag platta till formulär i ett PDF-dokument?

S: Att förenkla formulär är användbart när du vill bevara det visuella utseendet på formulärfält och anteckningar i ett PDF-dokument samtidigt som du hindrar användare från att ändra data. Detta görs vanligtvis när du vill dela ett PDF-dokument med förifyllda formulärdata eller kommentarer som inte bör ändras av mottagarna.

#### F: Kommer utjämningsformulär att påverka andra kommentarer, till exempel digitala signaturer?

S: Ja, platta formulär sammanfogar alla anteckningar, inklusive digitala signaturer, med PDF:s innehåll. När formulären är tillplattade kommer alla befintliga digitala signaturer att bli en permanent del av dokumentet, och användare kan inte ändra eller ta bort dem.

#### F: Kan jag selektivt platta ut specifika formulärfält och låta andra redigeras?

S: Ja, du kan selektivt förenkla specifika formulärfält i ett PDF-dokument samtidigt som andra kan redigeras. Istället för att använda koden för att platta till alla formulärfält kan du välja att bara platta till önskade formulärfält baserat på deras namn eller andra kriterier.