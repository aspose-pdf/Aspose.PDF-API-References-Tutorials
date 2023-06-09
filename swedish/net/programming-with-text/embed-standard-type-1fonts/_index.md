---
title: Bädda in standardtyp 1-teckensnitt
linktitle: Bädda in standardtyp 1-teckensnitt
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du bäddar in standardtyp 1-teckensnitt i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 140
url: /sv/net/programming-with-text/embed-standard-type-1fonts/
---

Denna handledning guidar dig genom processen att bädda in standardtyp 1-teckensnitt i ett PDF-dokument med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

## Krav
Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan C#-kompilator installerad på din maskin.
- Aspose.PDF för .NET-bibliotek. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda en pakethanterare som NuGet för att installera den.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnrymder
I kodfilen där du vill bädda in standardtyp 1-teckensnitt, lägg till följande med hjälp av direktivet överst i filen:

```csharp
using Aspose.Pdf;
```

## Steg 3: Ställ in dokumentkatalogen
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Ladda det befintliga PDF-dokumentet
 Ladda ett befintligt PDF-dokument med hjälp av`Document` konstruktorn och skickar sökvägen till indata-PDF-filen.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Steg 5: Ställ in egenskapen EmbedStandardFonts
 Ställ in`EmbedStandardFonts` handlingens egendom till`true` för att möjliggöra inbäddning av standardtyp 1-teckensnitt.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## Steg 6: Bädda in teckensnitt på varje sida
 Gå igenom varje sida i PDF-dokumentet och kontrollera om typsnitten redan är inbäddade. Om inte, ställ in`IsEmbedded` egendom till`true` för att bädda in typsnittet.

```csharp
foreach(Page page in pdfDocument.Pages)
{
     if (page.Resources.Fonts != null)
     {
         foreach(Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
         {
             if (!pageFont.IsEmbedded)
             {
                 pageFont.IsEmbedded = true;
             }
         }
     }
}
```

## Steg 7: Spara det uppdaterade PDF-dokumentet
 Spara det uppdaterade PDF-dokumentet med hjälp av`Save` metod för`Document` objekt, som anger utdatafilens sökväg.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Exempel på källkod för Embed Standard Type 1Fonts med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda ett befintligt PDF-dokument
Document pdfDocument = new Document(dataDir + "input.pdf");
// Ställ in EmbedStandardFonts-egenskapen för dokumentet
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Kontrollera om teckensnittet redan är inbäddat
			if (!pageFont.IsEmbedded)
			{
				pageFont.IsEmbedded = true;
			}
		}
	}
}
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

## Slutsats
Du har framgångsrikt bäddat in standardtyp 1-teckensnitt i ett PDF-dokument med Aspose.PDF för .NET. Den uppdaterade PDF-filen med inbäddade typsnitt har sparats på den angivna sökvägen för utdatafilen.