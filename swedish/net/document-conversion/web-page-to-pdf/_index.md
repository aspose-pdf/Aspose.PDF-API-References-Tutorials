---
title: Webbsida till PDF
linktitle: Webbsida till PDF
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera webbsida till PDF med Aspose.PDF för .NET.
type: docs
weight: 320
url: /sv/net/document-conversion/web-page-to-pdf/
---

I den här handledningen guidar vi dig steg för steg om hur du konverterar en webbsida till PDF med Aspose.PDF för .NET-biblioteket. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt. I slutet av denna handledning kommer du att kunna konvertera webbsidor till PDF-dokument utan ansträngning.

## Introduktion
Att konvertera webbsidor till PDF-format är ett vanligt krav i många applikationer. Genom att konvertera webbinnehåll till PDF kan du enkelt bevara layouten, formateringen och bilderna på den ursprungliga webbsidan. Aspose.PDF för .NET är ett kraftfullt bibliotek som låter dig utföra denna konvertering effektivt och korrekt.

## Krav
Innan vi börjar, se till att du har följande förutsättningar på plats:
- Visual Studio installerat på din dator
- Aspose.PDF för .NET-biblioteket (du kan ladda ner det från den officiella Aspose-webbplatsen)
- Grundläggande kunskaper i C#-programmering


## Steg 1: Definiera dokumentkatalogen
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Byta ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen där du vill spara den genererade PDF-filen.

## Steg 2: Skapa en webbförfrågan
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Skapa ett webbförfrågningsobjekt och ange webbadressen till webbsidan du vill konvertera. Du kan ersätta URL:en med vilken webbsida som helst.

## Steg 3: Få webbsvaret
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Skicka webbförfrågan och hämta svaret från servern.

## Steg 4: Läs webbinnehållet
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 Läs innehållet på webbsidan med a`StreamReader` och förvara den i`responseFromServer` variabel.

## Steg 5: Konvertera HTML till PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 Skapa en`MemoryStream` objekt för att ladda webbsidans innehåll. Skapa sedan en instans av`HtmlLoadOptions` och skicka webbsidans webbadress. Skapa sedan en`Document` objekt med den inlästa strömmen och HTML-laddningsalternativen. Ställ in`IsLandscape` egendom till`true` om du vill att PDF-filen ska vara i liggande riktning. Slutligen sparar du PDF-dokumentet i den angivna katalogen

.

## Steg 6: Hantera undantag
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
Fånga eventuella undantag som kan inträffa under konverteringsprocessen och visa felmeddelandet.

### Exempel på källkod för webbsida till PDF med Aspose.Words för .NET

```csharp
try
{
	
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Skapa en begäran om URL:en.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// Om det krävs av servern, ställ in autentiseringsuppgifterna.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Timeout i milisekunder innan begäran timeout
	// Request.Timeout = 100;

	// Få svaret.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Få strömmen som innehåller innehåll som returneras av servern.
	Stream dataStream = response.GetResponseStream();
	// Öppna streamen med en StreamReader för enkel åtkomst.
	StreamReader reader = new StreamReader(dataStream);
	// Läs innehållet.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// Ladda HTML-fil
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// Spara utdata som PDF-format
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats
den här handledningen har vi lärt oss hur man konverterar en webbsida till PDF med Aspose.PDF för .NET-biblioteket. Vi gick igenom den steg-för-steg-guide som förklarade den medföljande C#-källkoden. Genom att följa dessa instruktioner kan du enkelt integrera webbsida till PDF-konverteringsfunktioner i dina egna .NET-applikationer.