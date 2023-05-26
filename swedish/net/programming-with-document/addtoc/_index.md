---
title: Lägg till innehållsförteckning
linktitle: Lägg till innehållsförteckning
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du lägger till en innehållsförteckning till PDF-dokument med Aspose.PDF för .NET. Steg-för-steg guide med exempel på källkod. Öka dokumentnavigeringen!
type: docs
weight: 40
url: /sv/net/programming-with-document/addtoc/
---

I den här handledningen kommer vi att utforska hur du använder funktionen Lägg till TOC (innehållsförteckning) i Aspose.PDF för .NET för att lägga till en innehållsförteckning till PDF-dokument. Vi kommer att tillhandahålla en steg-för-steg-guide och förklara C#-källkoden som krävs för att uppnå detta. I slutet av denna handledning kommer du att kunna generera ett PDF-dokument med en innehållsförteckning med Aspose.PDF för .NET.


## Steg 1: Ladda den befintliga PDF-filen

För att komma igång måste vi ladda en befintlig PDF-fil. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din PDF-fil:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Steg 2: Skapa en ny sida för innehållsförteckningen

Vi kommer att skapa en ny sida för innehållsförteckningen. Följande kod infogar en ny sida vid index 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Steg 3: Definiera innehållsförteckningsinformationen

Därefter måste vi definiera innehållsförteckningsinformationen. Vi kommer att ställa in titeln och andra egenskaper för innehållsförteckningen. Lägg till följande kod:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Steg 4: Skapa TOC-element

Nu kommer vi att skapa elementen i innehållsförteckningen. I den här handledningen kommer vi att skapa fyra TOC-element som motsvarar olika sidor. Ändra följande kod enligt dina krav:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Steg 5: Spara det uppdaterade dokumentet

 Slutligen måste vi spara det ändrade dokumentet med innehållsförteckningen. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden nedan med den önskade sökvägen till utdatafilen:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Exempel på källkod för att lägga till TOC till PDF-dokument med Aspose.PDF för .NET

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda en befintlig PDF-fil
Document doc = new Document(dataDir + "AddTOC.pdf");

// Få tillgång till första sidan av PDF-filen
Page tocPage = doc.Pages.Insert(1);

// Skapa objekt för att representera TOC-information
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Ställ in titeln för TOC
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

// Skapa strängobjekt som kommer att användas som TOC-element
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Skapa rubrikobjekt
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Ange målsidan för rubrikobjektet
	heading2.DestinationPage = doc.Pages[i + 2];

	// Destinationssida
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Destinationskoordinat
	segment2.Text = titles[i];

	// Lägg till rubrik på sidan som innehåller innehållsförteckningen
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
//Spara det uppdaterade dokumentet
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);

```
