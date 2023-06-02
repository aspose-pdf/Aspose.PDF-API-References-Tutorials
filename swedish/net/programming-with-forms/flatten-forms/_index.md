---
title: Platta formulär
linktitle: Platta formulär
second_title: Aspose.PDF för .NET API Referens
description: Platta enkelt ut formulär i dina PDF-dokument med Aspose.PDF för .NET.
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

### Exempel på källkod för Flatten Forms med Aspose.Words för .NET 
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

den här handledningen lärde vi oss hur man plattar ut formulär med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt platta till formulär i dina PDF-dokument, göra fält oredigerbara och slå samman kommentarer med dokumentinnehåll.