---
title: Ta bort oanvända teckensnitt i PDF-fil
linktitle: Ta bort oanvända teckensnitt i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du tar bort oanvända teckensnitt i PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 300
url: /sv/net/programming-with-text/remove-unused-fonts/
---
den här handledningen kommer vi att förklara hur man tar bort oanvända teckensnitt i PDF-filer med Aspose.PDF-biblioteket för .NET. Vi kommer att gå igenom steg-för-steg-processen att ladda en PDF-fil, identifiera och ta bort oanvända teckensnitt och spara den uppdaterade PDF-filen med den medföljande C#-källkoden.

## Krav

Innan du börjar, se till att du har följande:

- Aspose.PDF för .NET-biblioteket installerat.
- En grundläggande förståelse för C#-programmering.

## Steg 1: Konfigurera dokumentkatalogen

 Först måste du ställa in sökvägen till katalogen där dina PDF-filer finns. Ersätta`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till dina PDF-filer.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda käll-PDF-filen

 Därefter laddar vi käll-PDF-dokumentet med hjälp av`Document` klass från Aspose.PDF-biblioteket.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Steg 3: Identifiera och ta bort oanvända teckensnitt

 Vi skapar en`TextFragmentAbsorber` objekt med`TextEditOptions` parameter satt till`TextEditOptions.FontReplace.RemoveUnusedFonts` . Det här alternativet låter oss identifiera och ta bort oanvända teckensnitt i PDF-dokumentet. Vi itererar sedan igenom alla`TextFragments` och ställ in typsnittet på önskat typsnitt.

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

### FAQ's

#### F: Vad är syftet med handledningen "Ta bort oanvända teckensnitt i PDF-fil"?

S: Handledningen "Ta bort oanvända teckensnitt i PDF-fil" förklarar hur du använder Aspose.PDF-biblioteket för .NET för att ta bort oanvända teckensnitt från ett PDF-dokument. Handledningen guidar dig genom processen att ladda en PDF-fil, identifiera och ta bort oanvända teckensnitt och spara den uppdaterade PDF-filen.

#### F: Varför skulle jag vilja ta bort oanvända teckensnitt från ett PDF-dokument?

S: Att ta bort oanvända teckensnitt från ett PDF-dokument kan hjälpa till att minska filstorleken och optimera dokumentet för bättre prestanda. Detta är särskilt användbart när du hanterar PDF-filer som innehåller inbäddade teckensnitt som faktiskt inte används i dokumentets innehåll.

#### F: Hur ställer jag in dokumentkatalogen?

S: Så här ställer du in dokumentkatalogen:

1.  Ersätta`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till katalogen där dina PDF-filer finns.

#### F: Hur tar jag bort oanvända teckensnitt från ett PDF-dokument med Aspose.PDF-biblioteket?

S: Handledningen guidar dig genom processen steg för steg:

1.  Öppna PDF-dokumentet med hjälp av`Document` klass.
2.  Skapa en`TextFragmentAbsorber` objekt med`TextEditOptions` inställd på`FontReplace.RemoveUnusedFonts`.
3. Acceptera absorbenten för att identifiera och ta bort oanvända teckensnitt från PDF:en.
4.  Iterera igenom allt`TextFragments` och ställ in typsnittet på önskat typsnitt.
5. Spara det uppdaterade PDF-dokumentet.

####  F: Vad är syftet med`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A: Den`TextEditOptions.FontReplace.RemoveUnusedFonts` parametern instruerar`TextFragmentAbsorber`för att identifiera och ta bort oanvända teckensnitt från PDF-dokumentet.

#### F: Kan jag ersätta oanvända typsnitt med ett valfritt typsnitt?

S: Ja, du kan ändra koden för att ersätta oanvända teckensnitt med ett valfritt teckensnitt. I den medföljande exempelkoden används typsnittet "Arial, Bold" som ersättning.

####  F: Hur fungerar`TextFragmentAbsorber` work to remove unused fonts?

 A: Den`TextFragmentAbsorber` är konfigurerad med`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter, som identifierar oanvända teckensnitt i textfragmenten i PDF-filen. Efter absorption kan du iterera dig igenom`TextFragments` och ställ in deras typsnitt till önskade ersättningsteckensnitt.

#### F: Vad är det förväntade resultatet av att exekvera den tillhandahållna koden?

S: Genom att följa handledningen och köra den medföljande C#-koden kommer du att ta bort oanvända teckensnitt från PDF-inmatningsdokumentet och spara den uppdaterade versionen som PDF-filen.

#### F: Kan jag ändra koden för att ta bort teckensnitt endast från specifika sidor eller områden?

S: Den medföljande koden fokuserar på att ta bort oanvända teckensnitt från hela PDF-dokumentet. Om du vill rikta in dig på specifika sidor eller regioner för borttagning av teckensnitt, måste du ändra tillvägagångssättet och använda mer komplex logik för att identifiera oanvända teckensnitt i dessa områden.