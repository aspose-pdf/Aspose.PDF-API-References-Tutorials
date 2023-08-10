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

 Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Skapa ett .NET Regex-objekt

 Skapa en`.NET Regex` objekt för att definiera sökmönstret:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Byta ut`@"[\S]+"` med ditt önskade reguljära uttrycksmönster.

## Steg 5: Ladda PDF-dokumentet

 Ladda PDF-dokumentet med hjälp av`Document` klass:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Byta ut`"SearchTextRegex.pdf"` med det faktiska namnet på din PDF-fil.

## Steg 6: Skaffa en specifik sida

Hämta önskad sida i dokumentet:

```csharp
Page page = document.Pages[1];
```

 Byta ut`1` med önskat sidnummer (1-baserat index).

## Steg 7: Skapa en TextFragmentAbsorber

 Skapa en`TextFragmentAbsorber`objekt för att hitta alla instanser av det inmatade reguljära uttrycket:

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