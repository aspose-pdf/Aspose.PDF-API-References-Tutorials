---
title: Sidnummer i sidhuvudet med hjälp av flytande låda
linktitle: Sidnummer i sidhuvudet med hjälp av flytande låda
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till sidnumret i sidhuvudet och sidfoten i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 150
url: /sv/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
I den här handledningen guidar vi dig steg för steg om hur du lägger till sidnummer i sidhuvud och sidfot i ett PDF-dokument med FloatingBox med Aspose.PDF för .NET. Vi kommer att använda den medföljande C#-källkoden för att skapa ett PDF-dokument, lägga till en sida, skapa en FloatingBox, ställa in dess position och lägga till sidnumret till den, spara sedan det modifierade PDF-dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Skapa PDF-dokumentet och lägga till en sida

Det första steget är att skapa en instans av PDF-dokumentet och lägga till en sida till det. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiera PDF-dokumentet
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Lägg till en sida i PDF-dokumentet
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där du vill spara PDF-dokumentet.

## Steg 3: Skapa FloatingBox och lägg till sidnumret

Nu när sidan har lagts till i PDF-dokumentet kan vi skapa en FloatingBox, ställa in dess position och lägga till sidnumret till den. Här är hur:

```csharp
// Skapa en FloatingBox med en bredd på 140 och en höjd på 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Ställ in styckets vänstra position
box1. Left = 2;

// Ställ in styckets översta position
box1. Top = 10;

// Lägg till sidnumret i FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Lägg till FloatingBox på sidan
page.Paragraphs.Add(box1);
```

Koden ovan skapar en FloatingBox med en bredd på 140 och en höjd på 80. Därefter ställer vi in dess position genom att ange de vänstra och övre värdena. Slutligen lägger vi till sidnumret i FloatingBox med hjälp av ett TextFragment som innehåller syntaxen "($p/ $P )" som kommer att ersättas med det aktuella sidnumret och det totala antalet sidor.

## Steg 4: Spara det ändrade PDF-dokumentet

När sidnumret har lagts till i sidhuvudet eller sidfoten med FloatingBox kan vi spara det modifierade PDF-dokumentet. Här är hur:

```csharp
// Spara det ändrade PDF-dokumentet
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Ovanstående kod sparar det redigerade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för sidnummer i sidhuvud med sidfot med flytande box med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera dokumentinstans
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Lägg till en sida i pdf-dokumentet
Aspose.Pdf.Page page = pdf.Pages.Add();

//Initierar en ny instans av FloatingBox-klassen
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Flytande värde som anger styckets vänstra position
box1.Left = 2;

// Flytande värde som anger styckets topposition
box1.Top = 10;

// Lägg till makron till styckesamlingen i FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Lägg till en floatingBox på sidan
page.Paragraphs.Add(box1);

// Spara dokumentet
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till sidnummer i sidhuvud och sidfot i PDF-dokument med FloatingBox med Aspose.PDF för .NET. Du kan nu anpassa dina sidhuvuden och sidfötter genom att lägga till dynamisk information som sidnummer.

### FAQ's

#### F: Vad är en FloatingBox och hur används den för att lägga till sidnummer i sidhuvudet eller sidfoten i ett PDF-dokument?

S: En FloatingBox är ett mångsidigt layoutelement i Aspose.PDF som kan innehålla olika innehåll, inklusive text och bilder. I den här handledningen används den för att skapa en behållare för sidnumret, så att du dynamiskt kan infoga det aktuella sidnumret och det totala antalet sidor i sidhuvudet eller sidfoten.

#### F: Hur kan den medföljande C#-källkoden lägga till sidnummer med en FloatingBox?

S: Kodavsnittet visar hur man skapar ett PDF-dokument, lägger till en sida, skapar en FloatingBox, ställer in dess position på sidan och infogar sidnumret med hjälp av ett TextFragment. Syntaxen "($p/ $P )" i TextFragmentet ersätts med nuvarande sidnummer och totalt antal sidor.

#### F: Kan jag anpassa utseendet och formateringen av sidnumret som lagts till med FloatingBox?

S: Ja, du kan anpassa utseendet på sidnumret genom att ändra egenskaperna för TextFragment i FloatingBox. Du kan ändra teckenstorlek, färg, stil, justering och andra formateringsalternativ.

#### F: Är det möjligt att lägga till olika dynamiska element, såsom datum och tid, i sidhuvudet eller sidfoten med ett liknande tillvägagångssätt?

S: Absolut, du kan lägga till olika dynamiska element som datum, tid, dokumentmetadata eller anpassad text genom att ändra TextFragment-innehållet i FloatingBox. Du kan använda makron som "($p/ $P )" för sidnummer eller "($date)" för det aktuella datumet.

#### F: Hur anger jag positionen för FloatingBox i sidhuvudet eller sidfoten?
 S: Den medföljande koden ställer in positionen för FloatingBox med hjälp av`Left` och`Top` egenskaper. Du kan justera dessa värden för att placera FloatingBox efter önskemål inom sidhuvudet eller sidfoten.

#### F: Kan jag använda ett annat teckensnitt eller stil för sidnumret i sidhuvudet eller sidfoten?

S: Ja, du kan anpassa teckensnitt, stil och andra formateringsegenskaper för sidnummertexten genom att ändra TextFragment-egenskaperna i FloatingBox.

#### F: Vad händer om innehållet i FloatingBox överskrider dess dimensioner?

S: Om innehållet i FloatingBox överskrider dess dimensioner, kan det skäras av eller layoutproblem kan uppstå. Se till att måtten på FloatingBox är lämpliga för innehållet och överväg att justera sidlayouten om det behövs.

#### F: Är det möjligt att lägga till flera FloatingBoxes med olika innehåll i sidhuvudet eller sidfoten på samma sida?

S: Ja, du kan lägga till flera FloatingBoxar med olika innehåll i sidhuvudet eller sidfoten på samma sida genom att skapa separata FloatingBox-instanser och lägga till dem i sidans Paragraphs-samling.

#### F: Kan jag använda FloatingBox-metoden för att lägga till innehåll till andra delar av PDF-dokumentet, till exempel brödtexten eller marginalerna?

S: Även om FloatingBoxes vanligtvis används för sidhuvuden och sidfötter, kan du också använda dem för att lägga till innehåll i andra delar av PDF-dokumentet, såsom brödtexten eller marginalerna, genom att placera dem på sidan.