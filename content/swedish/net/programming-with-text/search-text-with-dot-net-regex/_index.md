---
title: Sök text med Dot Net Regex
linktitle: Sök text med Dot Net Regex
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du söker efter text med reguljära .NET-uttryck i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 480
url: /sv/net/programming-with-text/search-text-with-dot-net-regex/
---
Denna handledning förklarar hur man använder Aspose.PDF för .NET för att söka efter text med .NET reguljära uttryck i ett PDF-dokument. Den medföljande C#-källkoden demonstrerar processen steg för steg.

## Förutsättningar

Innan du fortsätter med handledningen, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller använda NuGet för att installera det i ditt projekt.

## Steg 1: Konfigurera projektet

Börja med att skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnutrymmen

Lägg till följande med hjälp av direktiv i början av din C#-fil för att importera de nödvändiga namnrymden:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Steg 3: Ställ in sökvägen till dokumentkatalogen

 Ställ in sökvägen till din dokumentkatalog med hjälp av`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Skapa ett .NET Regex-objekt

 Skapa en`.NET Regex` objekt för att definiera sökmönstret:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Ersätta`@"[\S]+"` med ditt önskade reguljära uttrycksmönster.

## Steg 5: Ladda PDF-dokumentet

 Ladda PDF-dokumentet med hjälp av`Document` klass:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Ersätta`"SearchTextRegex.pdf"` med det faktiska namnet på din PDF-fil.

## Steg 6: Skaffa en specifik sida

Hämta önskad sida i dokumentet:

```csharp
Page page = document.Pages[1];
```

 Ersätta`1` med önskat sidnummer (1-baserat index).

## Steg 7: Skapa en TextFragmentAbsorber

 Skapa en`TextFragmentAbsorber` objekt för att hitta alla instanser av det inmatade reguljära uttrycket:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Steg 8: Acceptera absorbenten för sidan

Acceptera absorbenten för sidan:

```csharp
page.Accept(textFragmentAbsorber);
```

## Steg 9: Hämta de extraherade textfragmenten

 Hämta de extraherade textfragmenten med hjälp av`TextFragments` egendom av`TextFragmentAbsorber` objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Steg 10: Gå igenom textfragmenten

Gå igenom de hämtade textfragmenten och utför önskade åtgärder:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Ändra koden i slingan för att utföra ytterligare åtgärder på varje textfragment om det behövs.

### Exempel på källkod för söktext med Dot Net Regex med Aspose.PDF för .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Skapa Regex-objekt för att hitta alla ord
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Öppna dokumentet
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Skaffa en viss sida
Page page = document.Pages[1];
// Skapa TextAbsorber-objekt för att hitta alla instanser av indataregexet
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Acceptera absorbenten för sidan
page.Accept(textFragmentAbsorber);
// Hämta de extraherade textfragmenten
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Gå igenom fragmenten
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du söker efter text med reguljära .NET-uttryck i ett PDF-dokument med Aspose.PDF för .NET. Den här handledningen gav en steg-för-steg-guide, från att ställa in projektet till att komma åt de extraherade textfragmenten. Du kan nu infoga den här koden i dina egna C#-projekt för att utföra avancerade textsökningar i PDF-filer.

### FAQ's

#### F: Vad är syftet med handledningen "Sök text med Dot Net Regex"?

S: Handledningen "Sök text med Dot Net Regex" syftar till att vägleda användare hur de använder Aspose.PDF-biblioteket för .NET för att söka efter text i ett PDF-dokument med reguljära .NET-uttryck. Handledningen innehåller steg-för-steg-instruktioner och C#-kodexempel för att demonstrera processen.

#### F: Hur hjälper den här handledningen vid sökning efter text med reguljära .NET-uttryck i en PDF?

S: Denna handledning hjälper användare att förstå hur man kan utnyttja funktionerna i Aspose.PDF för .NET för att söka efter text med reguljära .NET-uttryck i ett PDF-dokument. Genom att följa stegen och kodexemplen kan användare effektivt söka efter textmönster som matchar deras angivna reguljära uttryck.

#### F: Vilka förutsättningar krävs för att följa denna handledning?

S: Innan du startar handledningen bör du ha en grundläggande förståelse för programmeringsspråket C#. Dessutom måste du ha Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller installera det i ditt projekt med NuGet.

#### F: Hur ställer jag in mitt projekt för att följa denna handledning?

S: Till att börja, skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket. Detta gör att du kan använda bibliotekets funktioner för att söka och arbeta med PDF-dokument.

#### F: Kan jag använda den här handledningen för att söka efter någon specifik typ av text med .NET reguljära uttryck?

 S: Ja, den här handledningen ger instruktioner om hur du söker efter text med .NET reguljära uttryck i ett PDF-dokument. Du kan anpassa`.NET Regex` objekt för att definiera det specifika sökmönster du vill använda.

#### F: Hur anger jag det reguljära uttrycksmönster för .NET som jag ska söka efter i den här handledningen?

 S: För att specificera .NET reguljära uttrycksmönster som du vill söka efter, skapa en`.NET Regex` objekt och ställ in dess mönster med hjälp av lämplig syntax för reguljära uttryck. Ersätt standard`@"[\S]+"` i handledningens kod med ditt önskade reguljära uttryck.

#### F: Hur hämtar jag egenskaperna för de extraherade textfragmenten?

 S: Efter att ha accepterat`TextFragmentAbsorber` för en specifik sida i PDF:en kan du hämta de extraherade textfragmenten med hjälp av`TextFragments` absorbatorobjektets egenskap. Detta ger tillgång till en samling textfragment som matchar det angivna reguljära uttrycket .NET.

#### F: Kan jag anpassa koden för att utföra ytterligare åtgärder på varje extraherat textfragment?

A: Visst. Handledningens exempelkod innehåller en loop för att iterera genom de hämtade textfragmenten. Du kan anpassa koden i denna loop för att utföra ytterligare åtgärder på varje extraherat textfragment baserat på dina projektkrav.

#### F: Hur sparar jag det ändrade PDF-dokumentet efter att ha extraherat textfragment?

S: Den här handledningen fokuserar i första hand på att söka efter text med .NET reguljära uttryck och att hämta textfragment. Om du tänker göra ändringar i PDF:en kan du hänvisa till annan Aspose.PDF-dokumentation för att lära dig hur du manipulerar och sparar dokumentet baserat på dina specifika behov.