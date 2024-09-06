---
title: Extrahera text från stämpelkommentar
linktitle: Extrahera text från stämpelkommentar
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du enkelt extraherar text från en stämpelkommentar i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 80
url: /sv/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
I den här handledningen tar vi dig steg för steg om hur du extraherar text från en stämpelkommentar i ett PDF-dokument med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att extrahera texten från en specifik stämpelkommentar på en viss sida i PDF-dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Laddar PDF-dokumentet

Det första steget är att ladda det befintliga PDF-dokumentet i ditt projekt. Så här gör du:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet
Document doc = new Document(dataDir + "test.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 3: Extrahera text från stämpelkommentaren

Nu när du har laddat PDF-dokumentet kan du extrahera texten från den specifika stämpelkommentaren. Så här gör du:

```csharp
// Hämta buffertkommentarer
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Skapa en textabsorbent
TextAbsorber ta = new TextAbsorber();

// Besök anteckningens utseende
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Visa den extraherade texten
Console.WriteLine(ta.Text);
```

Koden ovan hämtar stämpelkommentaren från den angivna sidan i PDF-dokumentet och använder sedan en textabsorbent för att extrahera texten från anteckningens utseende. Den extraherade texten visas sedan i utgången.

### Exempel på källkod för att extrahera text från stämpelkommentar med Aspose.PDF för .NET 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## Slutsats

Grattis! Du har lärt dig hur man extraherar text från en stämpelkommentar i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu använda den här metoden för att extrahera text från andra kommentarer i dina PDF-dokument.

### Vanliga frågor för att extrahera text från stämpelkommentarer

#### F: Vad är en stämpelkommentar i ett PDF-dokument, och varför skulle jag behöva extrahera text från det?

S: En stämpelkommentar i ett PDF-dokument är ett grafiskt element som kan användas för att ge ytterligare information, till exempel en vattenstämpel eller en gummistämpel. Att extrahera text från en stämpelkommentar är användbart när du vill hämta textbaserat innehåll från dessa anteckningar, som kan innehålla anteckningar, etiketter eller annan textinformation.

#### F: Hur extraherar den medföljande C#-källkoden text från en stämpelkommentar?

 S: Den medföljande källkoden visar hur man extraherar text från en specifik stämpelkommentar på en viss sida i ett PDF-dokument. Den använder Aspose.PDF-biblioteket för att hämta stämpelkommentaren, besöka dess utseende med en`TextAbsorber`, och visar sedan den extraherade texten i utdata.

#### F: Kan jag extrahera text från olika typer av kommentarer med ett liknande tillvägagångssätt?

S: Ja, du kan använda ett liknande tillvägagångssätt för att extrahera text från andra typer av kommentarer, till exempel textkommentarer eller popup-kommentarer. Du skulle behöva modifiera koden för att rikta in den specifika typen av anteckning som du vill extrahera text från.

####  F: Vad är syftet med`TextAbsorber` class in the code?

 A: Den`TextAbsorber` klass används för att extrahera text från olika delar av ett PDF-dokument, inklusive stämpelkommentarer. Den "absorberar" eller fångar textinnehållet som finns i det angivna området eller elementet i PDF-filen.

#### F: Hur identifierar jag den specifika stämpelkommentaren jag vill extrahera text från?

 S: I den medföljande koden identifieras stämpelkommentaren genom att gå till`Annotations` samling av en specifik sida och använda indexet för att hämta önskad anteckning. Du kan justera indexet eller använda andra kriterier för att identifiera målkommentaren.

#### F: Kan jag extrahera text från flera stämpelkommentarer på samma sida?

 S: Ja, du kan ändra koden så att den går igenom`Annotations`samling av en sida, filtrera bort stämpelkommentarer och extrahera text från var och en av dem.

#### F: Vad händer om stämpelkommentaren inte har något textinnehåll? Kommer koden fortfarande att fungera?

S: Koden kommer fortfarande att fungera, men den extraherar och visar en tom sträng om stämpelkommentarens utseende inte innehåller något textinnehåll.

#### F: Hur kan jag spara den extraherade texten till en fil istället för att visa den i utdata?

 S: Du kan ändra koden för att spara den extraherade texten till en fil istället för att visa den i konsolen. Byt bara ut`Console.WriteLine` uttalande med kod för att skriva texten till en fil.

#### F: Hur kan jag använda den extraherade texten i vidare bearbetning eller analys?

S: När du har extraherat texten med den tillhandahållna metoden kan du lagra den i en variabel, manipulera den, analysera den eller integrera den i andra delar av din applikation efter behov.