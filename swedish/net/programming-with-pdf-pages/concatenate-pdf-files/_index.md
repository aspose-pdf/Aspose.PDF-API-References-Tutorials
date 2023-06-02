---
title: Sammanfoga pdf-filer
linktitle: Sammanfoga pdf-filer
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att sammanfoga PDF-filer med Aspose.PDF för .NET. Lätt att följa och implementera i dina projekt.
type: docs
weight: 20
url: /sv/net/programming-with-pdf-pages/concatenate-pdf-files/
---
I den här handledningen går vi igenom steg-för-steg-processen för att sammanfoga PDF-filer med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du sammanfogar PDF-filer med Aspose.PDF för .NET.

## Förutsättningar
Innan du börjar, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#
- Aspose.PDF för .NET installerat i din utvecklingsmiljö

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det är här dina PDF-filer som ska sammanfogas finns. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Öppna PDF-filer
 Sedan kan du öppna PDF-filerna för att sammanfoga med hjälp av`Document` klass av Aspose.PDF. Var noga med att ange rätt sökväg till varje PDF-fil.

```csharp
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
```

## Steg 3: Sammanfoga sidor
 Nu kan du lägga till sidorna från det andra dokumentet till det första dokumentet med hjälp av`Add()` metod för dokumentet`Pages` samling. Detta kommer att sammanfoga sidorna i båda dokumenten till ett enda dokument.

```csharp
pdfDocument1.Pages.Add(pdfDocument2.Pages);
```

## Steg 4: Spara den sammanfogade PDF-filen
 Slutligen kan du spara det sammanlänkade PDF-dokumentet till en utdatafil med hjälp av dokumentets`Save()` metod. Var noga med att ange rätt sökväg och filnamn.

```csharp
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
pdfDocument1.Save(dataDir);
```

### Exempel på källkod för Sammanfoga PDF-filer med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna det första dokumentet
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
// Öppna det andra dokumentet
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
// Lägg till sidor i det andra dokumentet till det första
pdfDocument1.Pages.Add(pdfDocument2.Pages);
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
//Spara sammanlänkade utdatafil
pdfDocument1.Save(dataDir);
System.Console.WriteLine("\nPDFs are concatenated successfully.\nFile saved at " + dataDir);

```

## Slutsats
I den här handledningen lärde vi oss hur man sammanfogar PDF-filer med Aspose.PDF för .NET. Genom att följa stegen ovan kan du enkelt implementera denna funktion i dina egna projekt. Utforska gärna Aspose.PDF-dokumentationen ytterligare för att upptäcka andra användbara funktioner för att arbeta med PDF-filer.
