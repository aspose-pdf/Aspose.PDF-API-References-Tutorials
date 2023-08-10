---
title: Ta bort oanvända teckensnitt
linktitle: Ta bort oanvända teckensnitt
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du tar bort oanvända teckensnitt från ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 300
url: /sv/net/programming-with-text/remove-unused-fonts/
---

I den här handledningen kommer vi att förklara hur man tar bort oanvända teckensnitt från ett PDF-dokument med Aspose.PDF-biblioteket för .NET. Vi kommer att gå igenom steg-för-steg-processen att ladda en PDF-fil, identifiera och ta bort oanvända teckensnitt och spara den uppdaterade PDF-filen med den medföljande C#-källkoden.

## Krav

Innan du börjar, se till att du har följande:

- Aspose.PDF för .NET-biblioteket installerat.
- En grundläggande förståelse för C#-programmering.

## Steg 1: Konfigurera dokumentkatalogen

 Först måste du ställa in sökvägen till katalogen där dina PDF-filer finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till dina PDF-filer.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda käll-PDF-filen

 Därefter laddar vi käll-PDF-dokumentet med hjälp av`Document` klass från Aspose.PDF-biblioteket.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Steg 3: Identifiera och ta bort oanvända teckensnitt

 Vi skapar en`TextFragmentAbsorber` objekt med`TextEditOptions` parameter satt till`TextEditOptions.FontReplace.RemoveUnusedFonts` Det här alternativet låter oss identifiera och ta bort oanvända teckensnitt i PDF-dokumentet. Vi itererar sedan igenom alla`TextFragments` och ställ in typsnittet på önskat typsnitt.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Steg 4: Spara den uppdaterade PDF-filen

Slutligen sparar vi det uppdaterade PDF-dokumentet till den angivna utdatafilen.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Exempel på källkod för Ta bort oanvända teckensnitt med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ladda käll-PDF-fil
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Iterera igenom alla textfragment
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Spara uppdaterat dokument
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Slutsats

I den här handledningen har du lärt dig hur du tar bort oanvända teckensnitt från ett PDF-dokument med hjälp av Aspose.PDF-biblioteket för .NET. Genom att följa steg-för-steg-guiden och köra den medföljande C#-koden kan du ladda en PDF, identifiera och ta bort oanvända teckensnitt och spara den uppdaterade PDF-filen.