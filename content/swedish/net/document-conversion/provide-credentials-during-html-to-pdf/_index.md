---
title: Ge referenser under HTML till PDF
linktitle: Ge referenser under HTML till PDF
second_title: Aspose.PDF för .NET API-referens
description: Steg för steg guide för att konvertera HTML till PDF genom att tillhandahålla referenser med Aspose.PDF för .NET.
type: docs
weight: 240
url: /sv/net/document-conversion/provide-credentials-during-html-to-pdf/
---
den här handledningen kommer vi att leda dig genom processen att konvertera en HTML-fil till PDF samtidigt som vi tillhandahåller autentiseringsuppgifter när du kommer åt en säker URL med Aspose.PDF för .NET. Genom att följa stegen nedan kommer du att kunna konvertera HTML-innehåll till PDF med lämpliga referenser.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Hämta säkert HTML-innehåll
I det här steget hämtar vi säkert HTML-innehåll från en URL med hjälp av lämpliga uppgifter. Använd följande kod:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa en begäran om URL:en.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Om det behövs för servern, ställ in autentiseringsuppgifter.
request.Credentials = CredentialCache.DefaultCredentials;
// Få svaret.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Hämta strömmen som innehåller innehållet som returneras av servern.
Stream dataStream = response. GetResponseStream();
// Öppna streamen med en StreamReader för enkel åtkomst.
StreamReader reader = new StreamReader(dataStream);
// Läs innehållet.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där du vill spara den resulterande PDF-filen.

## Steg 2: Konvertera HTML till PDF genom att tillhandahålla referenser
Nu kommer vi att ladda det hämtade HTML-innehållet och konvertera det till PDF-format samtidigt som vi tillhandahåller lämpliga referenser. Använd följande kod:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Ladda HTML-filen
Document pdfDocument = new Document(stream, options);
```

## Steg 3: Spara den resulterande PDF-filen
Slutligen kommer vi att spara den resulterande PDF-filen. Använd följande kod:

```csharp
// Spara den resulterande PDF-filen
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Koden ovan sparar den resulterande PDF-filen med filnamnet`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Exempel på källkod för tillhandahålla referenser under HTML till PDF med Aspose.PDF för .NET

```csharp
try
{
	
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Skapa en begäran om URL:en.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Om det krävs av servern, ställ in autentiseringsuppgifterna.
	request.Credentials = CredentialCache.DefaultCredentials;
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

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Ladda HTML-fil
	Document pdfDocument = new Document(stream, options);
	// Spara den resulterande filen
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats
den här handledningen täckte vi steg-för-steg-processen att konvertera en HTML-fil till PDF samtidigt som vi tillhandahåller autentiseringsuppgifter när du kommer åt en säker URL med Aspose.PDF för .NET. Genom att följa instruktionerna ovan kommer du att framgångsrikt kunna konvertera HTML-innehåll till PDF samtidigt som du tillhandahåller rätt referenser.

### FAQ's

#### F: Vad är Aspose.PDF för .NET?

S: Aspose.PDF för .NET är ett robust bibliotek som ger utvecklare möjlighet att arbeta med PDF-dokument i C#-applikationer. Den erbjuder ett brett utbud av funktioner, inklusive HTML till PDF-konvertering.

#### F: Hur kan jag hämta säkert HTML-innehåll från en URL?

 S: För att hämta säkert HTML-innehåll från en URL kan du använda`WebRequest` klass i C#. Se till att ställa in lämpliga referenser med hjälp av`Credentials` fast egendom.

#### F: Vilka är förutsättningarna för denna handledning?

S: Innan du fortsätter med handledningen, se till att du har följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

#### F: Hur hanterar Aspose.PDF för .NET externa resurser samtidigt som HTML konverteras till PDF?

 A: Aspose.PDF för .NET tillhandahåller`HtmlLoadOptions`klass för att hantera externa resurser under HTML till PDF-konvertering. Du kan ställa in autentiseringsuppgifter för externa resurser med hjälp av`ExternalResourcesCredentials` fast egendom.

#### F: Kan jag anpassa filnamnet för den resulterande PDF-filen?

 S: Ja, du kan anpassa filnamnet för den resulterande PDF-filen genom att ändra koden som sparar PDF-dokumentet. Ändra helt enkelt önskat filnamn i`pdfDocument.Save()` metod.