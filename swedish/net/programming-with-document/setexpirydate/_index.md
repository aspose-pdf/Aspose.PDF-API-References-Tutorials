---
title: Ställ in utgångsdatum i PDF-fil
linktitle: Ställ in utgångsdatum i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in utgångsdatum i PDF-fil med Aspose.PDF för .NET med denna steg-för-steg-guide.
type: docs
weight: 300
url: /sv/net/programming-with-document/setexpirydate/
---
Aspose.PDF för .NET är ett kraftfullt bibliotek som tillhandahåller olika funktioner för att arbeta med PDF-filer. En sådan funktion är möjligheten att ställa in ett utgångsdatum för ett PDF-dokument. I den här handledningen går vi igenom processen att ställa in ett utgångsdatum för ett PDF-dokument med Aspose.PDF för .NET. 

## Steg 1: Ställ in sökvägen till dokumentkatalogen

Innan vi börjar måste vi ställa in sökvägen till katalogen där vårt PDF-dokument finns. Vi kommer att lagra denna sökväg i en variabel som heter "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett nytt PDF-dokument

 För att skapa ett nytt PDF-dokument måste vi instansiera ett nytt`Aspose.Pdf.Document` objekt. Vi kan göra detta med följande kod:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Steg 3: Lägga till en ny sida i PDF-dokumentet

När vi har skapat PDF-dokumentet kan vi lägga till en ny sida till det. Vi kan göra detta med följande kod:

```csharp
doc.Pages.Add();
```

## Steg 4: Lägga till text i PDF-dokumentet

Efter att ha lagt till en sida i PDF-dokumentet kan vi lägga till text till det med hjälp av`Paragraphs` samling. Vi kan göra detta med följande kod:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Steg 5: Ställ in PDF-utgångsdatum med JavaScript

För att ställa in PDF:s utgångsdatum måste vi skapa ett JavaScript-objekt. Vi kan göra detta med följande kod:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Ställ in JavaScript som PDF-öppningsåtgärd
doc.OpenAction = javaScript;
```

I den här koden anger vi utgångsdatumet till maj 2017.

## Steg 6: Spara PDF-filen

 När du har ställt in utgångsdatumet måste du spara PDF-filen. För att göra detta kan du använda`Save` metod för`Document` objekt och skicka in sökvägen till där du vill spara den uppdaterade PDF-filen.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Spara PDF-dokument
doc.Save(dataDir);
```

### Exempel på källkod för Ange utgångsdatum med Aspose.PDF för .NET

Här är den kompletta källkoden för att ställa in utgångsdatum med Aspose.PDF för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera dokumentobjekt
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Lägg till sida till sidor samling av PDF-fil
doc.Pages.Add();
// Lägg till textfragment till styckesamling av sidobjekt
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Skapa JavaScript-objekt för att ställa in PDF:s utgångsdatum
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Ställ in JavaScript som PDF-öppningsåtgärd
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Spara PDF-dokument
doc.Save(dataDir);
```

## Slutsats

Att ställa in ett utgångsdatum för ett PDF-dokument med Aspose.PDF för .NET är en användbar funktion för att säkerställa att dokumentet endast är giltigt under en viss period. Genom att följa steg-för-steg-guiden och använda den medföljande C#-källkoden kan utvecklare enkelt ställa in utgångsdatum och skapa PDF-filer med tidsbegränsad giltighet. Den här funktionen kan vara särskilt användbar för dokument som behöver nås eller distribueras under en begränsad tid.

### Vanliga frågor för inställt utgångsdatum i PDF-fil

#### F: Kan jag ställa in ett annat utgångsdatum för PDF-dokumentet?

 S: Ja, du kan ställa in ett annat utgångsdatum för PDF-dokumentet genom att ändra JavaScript-koden i steg 5. I det angivna exemplet är utgångsdatumet satt till maj 2017. För att ställa in ett annat utgångsdatum måste du ändra`year` och`month` variabler i JavaScript-koden till önskat år och månad.

#### F: Vad händer när PDF-dokumentet har upphört att gälla?

S: När PDF-dokumentet har upphört att gälla, enligt vad som anges i JavaScript-koden, kommer läsaren att visa ett varningsmeddelande som indikerar att filen är utgången och att användaren behöver en ny. Detta varningsmeddelande kommer att visas när PDF-filen öppnas.

#### F: Kan jag använda en specifik tid för utgångsdatumet istället för bara datumet?

 S: Ja, du kan ställa in en specifik tid för utgångsdatumet i JavaScript-koden. Genom att modifiera`expiry` variabel i JavaScript-koden för att inkludera önskad tid, kan du ställa in en specifik tid för utgångsdatumet.