---
title: Stryk ut ord
linktitle: Stryk ut ord
second_title: Aspose.PDF för .NET API Referens
description: Den här artikeln ger en steg-för-steg-guide för hur du använder Aspose.PDF för .NET:s Strike Out Words-funktion, inklusive steg-för-steg-guide och förklaringar
type: docs
weight: 150
url: /sv/net/annotations/strikeoutwords/
---
Aspose.PDF för .NET är ett bibliotek för manipulering och bearbetning av PDF-dokument som tillhandahåller olika funktioner för att skapa, ändra och konvertera PDF-filer. En av de användbara funktionerna som Aspose.PDF tillhandahåller är möjligheten att stryka ut ord eller fraser i ett PDF-dokument med hjälp av C#-källkoden. I den här artikeln kommer vi att ge en steg-för-steg-guide om hur man stryker ut ord med Aspose.PDF för .NET.

## Laddar PDF-dokumentet
Det första steget är att ladda PDF-dokumentet som du vill ändra. I den här handledningen kommer vi att ladda ett PDF-dokument med namnet "input.pdf" från mappen "DIN DOKUMENTKABEL". 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Söker efter textfragment
För att stryka specifika ord eller fraser i PDF-dokumentet måste du först söka efter dem. Aspose.PDF tillhandahåller en TextFragmentAbsorber-klass som kan användas för att söka efter ett specifikt textfragment i PDF-dokumentet.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

koden ovan söker vi efter textfragmentet "Estoque" i PDF-dokumentet. Du kan ändra detta för att söka efter andra ord eller fraser som du vill stryka.

## Att stryka ut textfragmenten
Efter att ha hittat textfragmenten är nästa steg att stryka ut dem. Aspose.PDF tillhandahåller en StrikeOutAnnotation-klass som kan användas för att skapa en överstruken kommentar för textfragmentet. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

I koden ovan skapar vi en överstruken kommentar för varje textfragment som vi hittade. Vi ställer också in opacitet, ram och färg för den genomstrukna annoteringen.

## Sparar det ändrade PDF-dokumentet
Efter att ha strykit ut textfragmenten sparar du det ändrade dokumentet.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Exempel på källkod för Strike Out Words med Aspose.PDF för .NET


```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document document = new Document(dataDir + "input.pdf");

// Skapa TextFragment Absorber-instans för att söka i ett visst textfragment
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Iterera genom sidor i PDF-dokument
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Hämta första sidan av PDF-dokument
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Skapa en samling av absorberad text
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Iterera på ovanstående samling
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Få rektangulära dimensioner på TextFragment-objekt
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Instantiera StrikeOut Annotation-instans
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Ställ in opacitet för anteckning
	strikeOut.Opacity = .80f;
	// Ställ in gränsen för anteckningsinstansen
	strikeOut.Border = new Border(strikeOut);
	// Ställ in färgen på anteckningen
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Lägg till anteckning till anteckningssamling av TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```
