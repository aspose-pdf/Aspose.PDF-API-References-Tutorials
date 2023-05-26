---
title: Ställ in zoomfaktor
linktitle: Ställ in zoomfaktor
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du ställer in zoomfaktorn för PDF-filer med Aspose.PDF för .NET med vår steg-för-steg-guide.
type: docs
weight: 340
url: /sv/net/programming-with-document/setzoomfactor/
---
Aspose.PDF för .NET är ett kraftfullt API som låter utvecklare arbeta med PDF-dokument i sina .NET-applikationer. En av funktionerna den ger är möjligheten att ställa in zoomfaktorn för ett PDF-dokument. I den här steg-för-steg-guiden kommer vi att förklara hur man använder Aspose.PDF för .NET för att ställa in zoomfaktorn för ett PDF-dokument med den medföljande C#-källkoden.

## Steg 1: Ställ in sökvägen till dokumentkatalogen

 Det första steget är att ställa in sökvägen till katalogen där PDF-dokumentet finns. Detta kan göras genom att ställa in`dataDir` variabel till katalogsökvägen. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ersätt "DIN DOKUMENTKATOGRAF" med den faktiska katalogsökvägen där ditt PDF-dokument finns.

## Steg 2: Instantiera ett nytt dokumentobjekt

För att arbeta med ett PDF-dokument med Aspose.PDF för .NET måste vi skapa ett nytt`Document` objekt och ladda in PDF-filen i det. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 Denna kod kommer att skapa en ny`Document` objekt och ladda PDF-filen med namnet "SetZoomFactor.pdf" från`dataDir` katalog in i den.

## Steg 3: Ställ in zoomfaktorn

 När`Document` objekt skapas, kan vi ställa in zoomfaktorn för PDF-dokumentet. I följande kod ställer vi in zoomfaktorn till 50%.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 Denna kod ställer in zoomfaktorn till 50 % genom att skapa en ny`GoToAction` föremål och passerar en`XYZExplicitDestination` objekt med en zoomfaktor på 50 %. De`OpenAction` egendom av`Document` objekt ställs sedan in på detta`GoToAction` objekt.

## Steg 4: Spara PDF-dokumentet

 Slutligen kan vi spara det ändrade PDF-dokumentet till en ny fil. I följande kod sparar vi PDF-dokumentet till en ny fil med namnet "Zoomed_pdf_out.pdf" i`dataDir` katalog.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

## Slutsats

Aspose.PDF för .NET ger ett enkelt och effektivt sätt att ställa in zoomfaktorn för ett PDF-dokument med hjälp av C#-kod. Genom att följa stegen ovan kan du enkelt ändra zoomfaktorn för alla PDF-dokument i ditt .NET-program.

### Exempel på källkod för Set Zoom Factor med Aspose.PDF för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instantiera nytt dokumentobjekt
	Document doc = new Document(dataDir + "SetZoomFactor.pdf");

	GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
	doc.OpenAction = action;
	dataDir = dataDir + "Zoomed_pdf_out.pdf";
	// Spara dokumentet
	doc.Save(dataDir);

```
