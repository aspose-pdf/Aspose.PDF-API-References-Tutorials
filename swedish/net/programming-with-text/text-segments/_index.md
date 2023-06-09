---
title: Textsegment
linktitle: Textsegment
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du söker efter specifika textsegment i ett PDF-dokument med hjälp av reguljära uttryck i Aspose.PDF för .NET.
type: docs
weight: 540
url: /sv/net/programming-with-text/text-segments/
---

Denna handledning förklarar hur du söker efter specifika textsegment i ett PDF-dokument med Aspose.PDF för .NET. Den medföljande C#-källkoden visar olika scenarier med reguljära uttryck.

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

## Steg 3: Använd TextFragmentAbsorber för textsökning

 Skapa en`TextFragmentAbsorber`objekt för att söka efter specifika textsegment med hjälp av reguljära uttryck:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## Steg 4: Utför textsökningar med reguljära uttryck

Utför textsökningar baserat på olika scenarier med hjälp av reguljära uttryck. Här är några exempel:

- Så här söker du efter en exakt ordmatchning: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- Så här söker du efter en sträng med versaler eller gemener: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```

- Så här söker du efter alla strängar i PDF-dokumentet: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

- Så här hittar du text efter en specifik sträng tills en radbrytning: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- Så här hittar du text efter en matchning med regex: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- Så här söker du efter hyperlänkar/webbadresser i PDF-dokumentet: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

Ersätt de reguljära uttrycken med dina önskade sökmönster.

## Steg 5: Utför sökningen och bearbeta resultaten

 Utför sökningen med hjälp av den skapade`TextFragmentAbsorber` objekt och bearbeta resultaten utifrån dina krav.

### Exempel på källkod för textsegment med Aspose.PDF för .NET 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// För att söka exakt matchning av ett ord kan du överväga att använda reguljära uttryck.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
//För att söka i en sträng med antingen versaler eller gemener kan du överväga att använda reguljära uttryck.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
// För att söka i alla strängar (tolka alla strängar) i PDF-dokument, försök att använda följande reguljära uttryck.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// Hitta matchning av söksträngen och få vad som helst efter strängen till radbrytning.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// Använd följande reguljära uttryck för att hitta text som följer matchningen med regex.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// För att söka efter hyperlänkar/webbadresser i PDF-dokument, försök att använda följande reguljära uttryck.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du söker efter specifika textsegment i ett PDF-dokument med Aspose.PDF för .NET. Den här handledningen gav exempel på olika sökscenarier med reguljära uttryck. Du kan nu infoga den här koden i dina egna C#-projekt för att söka och bearbeta textsegment i PDF-filer.