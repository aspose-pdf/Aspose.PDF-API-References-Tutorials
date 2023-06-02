---
title: Skaffa Zoom Factor
linktitle: Skaffa Zoom Factor
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder Aspose.PDF för .NET för att få zoomfaktorn för en PDF-fil med denna steg-för-steg-guide.
type: docs
weight: 210
url: /sv/net/programming-with-document/getzoomfactor/
---
Aspose.PDF för .NET är ett PDF-manipuleringsbibliotek som tillhandahåller många funktioner för att utföra olika operationer på PDF-dokument. En av dessa funktioner är möjligheten att få zoomfaktorn för en PDF-fil. I den här handledningen kommer vi att förklara hur man använder Aspose.PDF för .NET för att få zoomfaktorn för en PDF-fil med C#-källkoden.


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

 Nästa steg är att skapa en`GoToAction` objekt. A`GoToAction` objekt representerar en åtgärd som går till en specifik destination i ett PDF-dokument. I vårt fall vill vi få zoomfaktorn för PDF-filen, så vi kommer att använda`OpenAction` egendom av`Document` objekt för att få`GoToAction` objekt.

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

 I ovanstående kod har vi tillgång till`Destination` egendom av`GoToAction` objekt och sedan kasta det till`XYZExplicitDestination` . Efter det har vi kommit åt`Zoom` egendom av`XYZExplicitDestination` objekt för att få PDF-filens zoomfaktor.

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
