---
title: Ordna om innehållet med hjälp av textersättning
linktitle: Ordna om innehållet med hjälp av textersättning
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ordnar om innehållet i ett PDF-dokument med hjälp av textersättning med Aspose.PDF för .NET.
type: docs
weight: 270
url: /sv/net/programming-with-text/rearrange-contents-using-text-replacement/
---

den här handledningen kommer vi att förklara hur man ordnar om innehållet i ett PDF-dokument genom att använda textersättning med Aspose.PDF-biblioteket för .NET. Vi kommer att gå igenom steg-för-steg-processen att ladda en PDF-fil, söka efter specifika textfragment, ersätta texten och spara den modifierade PDF-filen med den medföljande C#-källkoden.

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
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Steg 3: Sök och ersätt textfragment

 Vi skapar en`TextFragmentAbsorber` objekt med ett reguljärt uttryck för att söka efter specifika textfragment. Sedan itererar vi genom textfragmenten, anpassar deras teckensnitt, storlek, färg och ersätter texten.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## Steg 4: Spara den modifierade PDF-filen

Slutligen sparar vi det modifierade PDF-dokumentet till den angivna utdatafilen.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Exempel på källkod för Ordna om innehåll med hjälp av textersättning med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ladda käll-PDF-fil
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	//Skapa TextFragment Absorber-objekt med reguljärt uttryck
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Byt ut varje TextFragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Ställ in teckensnitt för textfragment som ersätts
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Ställ in teckenstorlek
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Ersätt texten med en större sträng än platshållaren
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Spara resulterande PDF
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Slutsats

I den här handledningen har du lärt dig hur du ordnar om innehållet i ett PDF-dokument genom att använda textersättning med Aspose.PDF-biblioteket för .NET. Genom att följa den steg-för-steg-guide och köra den medföljande C#-koden kan du söka efter specifika textfragment, anpassa deras utseende och ersätta texten i ett PDF-dokument.