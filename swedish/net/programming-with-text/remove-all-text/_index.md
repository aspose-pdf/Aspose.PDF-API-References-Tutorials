---
title: Ta bort all text
linktitle: Ta bort all text
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du tar bort all text från ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 280
url: /sv/net/programming-with-text/remove-all-text/
---

I den här handledningen kommer vi att förklara hur man tar bort all text från ett PDF-dokument med hjälp av Aspose.PDF-biblioteket för .NET. Vi kommer att gå igenom steg-för-steg-processen för att öppna en PDF, välja och ta bort text från varje sida och spara den modifierade PDF-filen med den medföljande C#-källkoden.

## Krav

Innan du börjar, se till att du har följande:

- Aspose.PDF för .NET-biblioteket installerat.
- En grundläggande förståelse för C#-programmering.

## Steg 1: Konfigurera dokumentkatalogen

 Först måste du ställa in sökvägen till katalogen där dina PDF-filer finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till dina PDF-filer.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet

 Därefter öppnar vi PDF-dokumentet med hjälp av`Document` klass från Aspose.PDF-biblioteket.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Steg 3: Ta bort text från varje sida

 Vi går igenom alla sidor i PDF-dokumentet och använder en`OperatorSelector` för att markera all text på varje sida. Sedan tar vi bort den markerade texten.

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## Steg 4: Spara den modifierade PDF-filen

Slutligen sparar vi det modifierade PDF-dokumentet till den angivna utdatafilen.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Exempel på källkod för Ta bort all text med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Bläddra igenom alla sidor i PDF-dokument
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	// Markera all text på sidan
	page.Contents.Accept(operatorSelector);
	// Ta bort all text
	page.Contents.Delete(operatorSelector.Selected);
}
// Spara dokumentet
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Slutsats

den här handledningen har du lärt dig hur du tar bort all text från ett PDF-dokument med Aspose.PDF-biblioteket för .NET. Genom att följa steg-för-steg-guiden och köra den medföljande C#-koden kan du öppna en PDF, välja och ta bort text från varje sida och spara den ändrade PDF-filen.