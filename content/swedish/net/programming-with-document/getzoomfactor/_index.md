---
title: Hämta Zoom Factor i PDF-fil
linktitle: Hämta Zoom Factor i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du använder Aspose.PDF för .NET för att få zoomfaktorn i PDF-fil med denna steg-för-steg-guide.
type: docs
weight: 210
url: /sv/net/programming-with-document/getzoomfactor/
---
Aspose.PDF för .NET är ett PDF-manipuleringsbibliotek som tillhandahåller många funktioner för att utföra olika operationer på PDF-dokument. En av dessa funktioner är möjligheten att få zoomfaktorn i PDF-fil. I den här handledningen kommer vi att förklara hur man använder Aspose.PDF för .NET för att få zoomfaktorn i PDF-filen med C#-källkoden.


## Steg 1: Instantiera nytt dokumentobjekt

 Det första steget för att få zoomfaktorn för en PDF-fil med Aspose.PDF för .NET är att instansiera en ny`Document` objekt. De`Document` objekt representerar ett PDF-dokument som kan laddas från en fil eller en ström.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera nytt dokumentobjekt
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 I ovanstående kod har vi skapat en`Document` objekt genom att skicka sökvägen till PDF-filen till konstruktören av`Document` klass. Du måste ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där din PDF-fil finns.

## Steg 2: Skapa GoToAction-objekt

 Nästa steg är att skapa en`GoToAction` objekt. A`GoToAction`objekt representerar en åtgärd som går till en specifik destination i ett PDF-dokument. I vårt fall vill vi få zoomfaktorn för PDF-filen, så vi kommer att använda`OpenAction` egendom av`Document` objekt för att få`GoToAction` objekt.

```csharp
// Skapa GoToAction-objekt
GoToAction action = doc.OpenAction as GoToAction;
```

 I ovanstående kod har vi skapat en`GoToAction` objekt genom att gjuta`OpenAction` egendom av`Document` invända mot`GoToAction`.

## Steg 3: Hämta zoomfaktorn för PDF-filen

 Det tredje steget är att få PDF-filens zoomfaktor. Vi kan få zoomfaktorn för PDF-filen genom att gå till`Destination` egendom av`GoToAction` objekt och sedan gjuta det till`XYZExplicitDestination` . De`XYZExplicitDestination` klass representerar en destination i ett PDF-dokument som anger koordinaterna och zoomfaktorn att gå till.

```csharp
// Hämta zoomfaktorn för PDF-filen
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Dokumentzoomvärde;
```

 I ovanstående kod har vi tillgång till`Destination` egendom av`GoToAction` objekt och sedan kasta det till`XYZExplicitDestination` . Efter det har vi kommit åt`Zoom` egendom av`XYZExplicitDestination` objekt för att få zoomfaktorn för PDF-filen.

## Steg 4: Mata ut zoomfaktorn

 Det sista steget är att mata ut zoomfaktorn för PDF-filen. Vi kan använda`System.Console.WriteLine`

```csharp
// Hämta zoomfaktorn för PDF-filen
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Dokumentzoomvärde;
```        

### Exempel på källkod för Get Zoom Factor med Aspose.PDF för .NET

Här är den kompletta källkoden för Get Zoom Factor med Aspose.PDF för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera nytt dokumentobjekt
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Skapa GoToAction-objekt
GoToAction action = doc.OpenAction as GoToAction;

// Hämta zoomfaktorn för PDF-filen
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Dokumentzoomvärde;
```

## Slutsats

I den här handledningen har vi utforskat hur man använder Aspose.PDF för .NET för att få zoomfaktorn för en PDF-fil. Zoomfaktorn är en avgörande aspekt av ett PDF-dokument, eftersom den bestämmer den initiala visningsstorleken när den öppnas i en visningsprogram. Genom att komma åt och använda zoomfaktorn kan utvecklare anpassa visningsupplevelsen för slutanvändare. Aspose.PDF för .NET tillhandahåller ett enkelt och effektivt API för att hämta zoomfaktorn och annan navigeringsrelaterad information från ett PDF-dokument, vilket ger utvecklare möjlighet att bygga funktionsrika och interaktiva PDF-applikationer.

### Vanliga frågor för att få zoomfaktor i PDF-fil

#### F: Vad är zoomfaktorn i en PDF-fil?

S: Zoomfaktorn i en PDF-fil hänvisar till förstoringsgraden som tillämpas på dokumentet när det visas. Den bestämmer den initiala visningsstorleken för PDF-filen på skärmen. En zoomfaktor på 1,0 representerar den faktiska storleken (100 % zoom), medan en zoomfaktor större än 1,0 representerar en förstoring och en zoomfaktor mindre än 1,0 representerar en förminskning.

#### F: Hur kan jag använda zoomfaktorinformationen i min applikation?

S: Du kan använda zoomfaktorinformationen för att anpassa den ursprungliga visningsstorleken för ett PDF-dokument när det öppnas i en visningsprogram. Du kan till exempel ställa in en specifik zoomfaktor för att säkerställa att PDF-filen visas i en viss storlek eller anpassa hela sidan till tittarens fönster.

#### F: Kan jag ändra zoomfaktorn för ett PDF-dokument programmatiskt med Aspose.PDF för .NET?

 S: Ja, du kan ändra zoomfaktorn för ett PDF-dokument programmatiskt med Aspose.PDF för .NET. Du kan ställa in zoomfaktorn för specifika åtgärder, som t.ex`GoToAction` eller`GoToRemoteAction`för att styra hur dokumentet visas när användaren interagerar med länkar eller bokmärken.

#### F: Finns det andra sätt att navigera till specifika platser i ett PDF-dokument med Aspose.PDF för .NET?

 S: Ja, Aspose.PDF för .NET tillhandahåller olika funktioner för att navigera till specifika platser i ett PDF-dokument. Förutom att använda`GoToAction` , kan du använda andra åtgärder som`GoToURIAction` för att öppna en URL,`GoToEmbeddedAction` för att navigera till inbäddade filer, och`GoToNamedAction` för att gå till namngivna destinationer i PDF-dokumentet.