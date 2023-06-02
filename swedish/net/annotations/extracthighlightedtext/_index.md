---
title: Extrahera markerad text
linktitle: Extrahera markerad text
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar markerad text med Aspose.PDF för .NET med denna steg-för-steg-guide.
type: docs
weight: 60
url: /sv/net/annotations/extracthighlightedtext/
---
För att extrahera markerad text från ett PDF-dokument kan du använda Aspose.PDF för .NET API. Detta API ger ett enkelt sätt att hämta all text som har markerats i ett dokument.

## Steg 1: Ladda PDF-dokumentet

 Det första steget för att extrahera markerad text från ett PDF-dokument är att ladda dokumentet med Aspose.PDF för .NET API. Du kan göra detta genom att skapa en ny instans av`Document` klass och skicka sökvägen till PDF-dokumentet som en parameter. 

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Steg 2: Gå igenom alla kommentarer

 Nästa steg är att gå igenom alla anteckningar i PDF-dokumentet. Du kan göra detta med hjälp av en`foreach` loop, så här:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Koden går här
}
```

## Steg 3: Filtrera textmarkeringskommentarer

 Inuti`foreach` loop måste du filtrera bort alla kommentarer som inte är textmarkeringskommentarer. Du kan göra detta genom att kontrollera om anteckningen är en instans av`TextMarkupAnnotation` klass.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Koden går här
}
```

## Steg 4: Hämta markerade textfragment

 När du har filtrerat bort alla textmarkeringskommentarer kan du hämta de markerade textfragmenten för varje anteckning. Du kan göra detta genom att ringa`GetMarkedTextFragments()` metod på`TextMarkupAnnotation` objekt.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Steg 5: Visa den markerade texten

 Slutligen kan du visa den markerade texten för användaren. Du kan göra detta genom att gå igenom varje`TextFragment` objekt i`TextFragmentCollection` och ringer till`Text` fast egendom.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Exempel på källkod för extrahera markerad text med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

