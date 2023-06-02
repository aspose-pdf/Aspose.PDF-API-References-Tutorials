---
title: Ställ in standardteckensnitt
linktitle: Ställ in standardteckensnitt
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in standardteckensnittet för ett PDF-dokument med Aspose.PDF för .NET med denna steg-för-steg-guide.
type: docs
weight: 280
url: /sv/net/programming-with-document/setdefaultfont/
---
Om du arbetar med PDF-dokument i .NET kan du stöta på problem där teckensnittet som används i PDF:en inte är tillgängligt på systemet där det visas eller skrivs ut. Detta kan resultera i att texten visas felaktigt eller inte alls. Aspose.PDF för .NET ger en lösning på detta problem genom att du kan ställa in ett standardteckensnitt för dokumentet. I det här exemplet, hur man ställer in standardteckensnittet med Aspose.PDF för .NET.

## Steg 1: Ställ in sökvägen till dokumentkatalogen

vi måste ställa in sökvägen till katalogen där vårt PDF-dokument finns. Vi kommer att lagra denna sökväg i en variabel som heter "dataDir".

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda PDF-dokumentet

 Vi börjar med att ladda ett befintligt PDF-dokument som saknar teckensnitt. I det här exemplet antar vi att PDF-dokumentet finns i den katalog som anges av`dataDir` variabel.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // koden går här
}
```

## Steg 3: Ställ in standardteckensnittet

 Därefter ställer vi in standardteckensnittet för PDF-dokumentet med hjälp av`PdfSaveOptions` klass. I det här exemplet ställer vi in standardteckensnittet till "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Steg 4: Spara det uppdaterade dokumentet

Slutligen sparar vi det uppdaterade dokumentet i en ny fil. I det här exemplet sparar vi det uppdaterade dokumentet till en fil med namnet "output_out.pdf" i samma katalog som indatafilen.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Exempel på källkod för Set Default Font med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda ett befintligt PDF-dokument med saknat teckensnitt
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Ange standardteckensnittsnamn
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```
