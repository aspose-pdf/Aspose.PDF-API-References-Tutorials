---
title: Lägg till innehållsförteckning till PDF-fil
linktitle: Lägg till innehållsförteckning till PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till en innehållsförteckning till en PDF-fil med Aspose.PDF för .NET. Steg-för-steg guide med exempel på källkod. Öka dokumentnavigeringen!
type: docs
weight: 40
url: /sv/net/programming-with-document/addtoc/
---
I den här handledningen kommer vi att utforska hur man använder funktionen Lägg till TOC (innehållsförteckning) till PDF-fil i Aspose.PDF för .NET för att lägga till en innehållsförteckning till PDF-dokument. Vi kommer att tillhandahålla en steg-för-steg-guide och förklara C#-källkoden som krävs för att uppnå detta. I slutet av denna handledning kommer du att kunna generera ett PDF-dokument med en innehållsförteckning med Aspose.PDF för .NET.


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

//Skapa strängobjekt som kommer att användas som TOC-element
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
// Spara det uppdaterade dokumentet
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Slutsats

I den här handledningen undersökte vi hur man lägger till en innehållsförteckning (TOC) till PDF-dokument med Aspose.PDF för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande C#-källkoden kan du enkelt skapa ett PDF-dokument med en innehållsförteckning. TOC förbättrar dokumentets användbarhet, så att användare kan navigera till specifika avsnitt eller sidor mer effektivt. Aspose.PDF för .NET ger en robust och användarvänlig lösning för att arbeta med PDF-filer i .NET-applikationer, vilket gör att du enkelt kan skapa dynamiska och interaktiva PDF-dokument.

### Vanliga frågor för att lägga till innehållsförteckning till PDF-fil

#### F: Vad är Aspose.PDF för .NET?

S: Aspose.PDF för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att effektivt arbeta med PDF-filer i .NET-applikationer. Den tillhandahåller ett brett utbud av funktioner för att skapa, manipulera och hantera PDF-dokument programmatiskt.

#### F: Vad är syftet med att lägga till en innehållsförteckning (TOC) till ett PDF-dokument?

S: Innehållsförteckningen (TOC) tillhandahåller ett navigeringshjälpmedel för användare, vilket gör att de snabbt kan hoppa till specifika avsnitt eller sidor i PDF-dokumentet. Det förbättrar dokumentets användbarhet och användarupplevelse.

#### F: Hur lägger jag till en innehållsförteckning till ett PDF-dokument med Aspose.PDF för .NET?

S: För att lägga till en innehållsförteckning till ett PDF-dokument med Aspose.PDF för .NET, måste du skapa en ny sida för innehållsförteckningen, definiera innehållsförteckningsinformationen och sedan skapa innehållsförteckningselement som motsvarar specifika sidor eller avsnitt i dokumentet.

#### F: Kan jag anpassa utseendet på innehållsförteckningen?

S: Ja, du kan anpassa utseendet på innehållsförteckningen genom att ställa in olika egenskaper för TOC-elementen, såsom teckenstorlek, typsnittsstil och justering. Aspose.PDF för .NET ger flexibilitet vid utformningen av innehållsförteckningen för att matcha ditt önskade utseende och känsla.

#### F: Är Aspose.PDF för .NET lämpligt för att lägga till avancerade funktioner till PDF-dokument?

S: Absolut, Aspose.PDF för .NET är ett funktionsrikt bibliotek som låter dig lägga till avancerade funktioner till PDF-dokument, inklusive interaktiva element, formulärfält, digitala signaturer och mer.