---
title: Ställ in standardteckensnitt i PDF-fil
linktitle: Ställ in standardteckensnitt i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du ställer in standardteckensnittet i en PDF-fil med Aspose.PDF för .NET med denna steg-för-steg-guide.
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

## Slutsats

Att ställa in ett standardteckensnitt i PDF-dokument med Aspose.PDF för .NET är ett enkelt och effektivt sätt att säkerställa att texten visas korrekt, även om de ursprungliga typsnitten inte är tillgängliga. Genom att följa den steg-för-steg-guide och använda den medföljande C#-källkoden kan utvecklare enkelt ställa in standardteckensnittet och skapa PDF-filer som erbjuder en konsekvent och pålitlig visningsupplevelse i olika miljöer. Den här funktionen är särskilt användbar i scenarier där PDF-filerna kommer att visas eller skrivas ut på olika system som kan ha olika teckensnitt installerade.

### Vanliga frågor för inställt standardteckensnitt i PDF-fil

#### F: Varför är det viktigt att ställa in ett standardteckensnitt i PDF-dokument?

S: Att ställa in ett standardteckensnitt i PDF-dokument är viktigt eftersom det säkerställer att texten kommer att visas korrekt även om de ursprungliga teckensnitten inte är tillgängliga på systemet där PDF-filen visas eller skrivs ut. Det hjälper till att förhindra problem som saknad eller förvrängd text, vilket säkerställer en konsekvent och pålitlig tittarupplevelse.

#### F: Kan jag välja vilket typsnitt som helst som standardteckensnitt med Aspose.PDF för .NET?

 S: Ja, du kan välja vilket typsnitt som helst som är tillgängligt på systemet som standardteckensnitt med Aspose.PDF för .NET. Ange helt enkelt namnet på teckensnittet i`DefaultFontName` egendom av`PdfSaveOptions` klass.

#### F: Vad händer om det angivna standardteckensnittet inte är tillgängligt på systemet?

S: Om det angivna standardteckensnittet inte är tillgängligt i systemet kommer PDF-läsaren att använda ett reservteckensnitt för att visa texten. Det är tillrådligt att välja ett allmänt tillgängligt typsnitt som Arial eller Times New Roman för att säkerställa kompatibilitet mellan olika system.