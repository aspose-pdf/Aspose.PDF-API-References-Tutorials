---
title: Få hyperlänkdestinationer
linktitle: Få hyperlänkdestinationer
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar hyperlänksdestinationer från en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 60
url: /sv/net/programming-with-links-and-actions/get-hyperlink-destinations/
---

Aspose.PDF för .NET är ett kraftfullt bibliotek för att manipulera och extrahera information från PDF-filer med programmeringsspråket C#. I den här handledningen kommer vi att fokusera på att extrahera hyperlänkdestinationer från en PDF-fil med Aspose.PDF för .NET.

## Förutsättningar

Innan du börjar, se till att du har följande:

- En integrerad utvecklingsmiljö (IDE) som Visual Studio.
- Aspose.PDF-biblioteket för .NET installerat på din maskin.

## Steg 1: Konfigurera utvecklingsmiljön

Innan du börjar skriva kod måste du ställa in din utvecklingsmiljö genom att skapa ett nytt C#-projekt i din favorit-IDE.

## Steg 2: Importera Aspose.PDF-referenser

För att använda Aspose.PDF för .NET måste du lägga till lämpliga referenser till ditt projekt. Följ stegen nedan för att importera nödvändiga referenser:

1. I ditt projekt högerklickar du på "Referenser" och väljer "Lägg till referens".
2. I fönstret "Lägg till referens", leta upp och välj DLL-filerna för Aspose.PDF för .NET.
3. Klicka på "OK" för att importera referenserna till ditt projekt.

## Steg 3: Laddar PDF-filen

Innan du kan extrahera hyperlänkdestinationer måste du ladda PDF-filen i din applikation. Använd följande kod för att ladda PDF-filen:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ladda PDF-filen
Document document = new Document(dataDir + "input.pdf");
```

Var noga med att ange rätt sökväg till din dokumentkatalog och PDF-filen du vill bearbeta.

## Steg 4: Navigera på sidorna i dokumentet

Nu när PDF-filen är laddad måste du gå igenom alla sidor i dokumentet. Detta gör att du kan få

ir hyperlänksanteckningarna som finns på varje sida. Använd följande kod för att iterera genom dokumentets sidor:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Få länkkommentarer för en specifik sida
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Skapa en lista för att lagra alla länkar
     IList<Annotation> list = selector. Selected;
     // Gå igenom varje objekt i listan
     foreach(LinkAnnotation a in list)
     {
         // Skriv ut måladress
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Denna kod går igenom varje sida i dokumentet och väljer hyperlänksanteckningarna som finns på varje sida. Sedan lagrar den dessa kommentarer i en lista och skriver ut måladressen för varje länk.

## Steg 5: Få hyperlänkdestinationer

Det sista steget är att extrahera hyperlänkdestinationerna från hyperlänksanteckningarna. Följande kod visar hur du gör:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Använd destinationen som du vill
     }
}
```

I den här koden får vi varje hyperlänkdestination från länkanteckningarna och lagrar destinationen i en variabel. Du kan sedan använda denna destination som du vill i din ansökan.

### Exempel på källkod för Get Hyperlink Destinations med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ladda PDF-filen
	Document document = new Document(dataDir + "input.pdf");
	// Gå igenom hela PDF-sidan
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Få länkkommentarerna från en viss sida
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Skapa en lista med alla länkar
		IList<Annotation> list = selector.Selected;
		// Iterera genom invidiaul objekt i listan
		foreach (LinkAnnotation a in list)
		{
			// Skriv ut måladressen
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```