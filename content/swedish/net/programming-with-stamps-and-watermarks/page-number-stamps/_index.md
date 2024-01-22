---
title: Sidnummerstämplar i PDF-fil
linktitle: Sidnummerstämplar i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du lägger till sidnummerstämplar i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 160
url: /sv/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
I den här handledningen guidar vi dig steg för steg om hur du lägger till sidnummerstämplar i PDF-fil med Aspose.PDF för .NET. Vi använder den medföljande C#-källkoden för att öppna ett befintligt PDF-dokument, skapa en sidnummerstämpel, ställa in dess egenskaper och lägga till den på en specifik sida i PDF-filen.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Laddar det befintliga PDF-dokumentet

Det första steget är att ladda det befintliga PDF-dokumentet i ditt projekt. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öppna det befintliga PDF-dokumentet
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 3: Skapa och konfigurera sidnumreringsstämpeln

Nu när PDF-dokumentet är laddat kan vi skapa en sidnumreringsbuffert och konfigurera den efter våra behov. Här är hur:

```csharp
// Skapa en sidnummerbuffert
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Definiera om bufferten är i bakgrunden eller inte
pageNumberStamp.Background = false;

// Format för sidnumreringsbufferten
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Nedre marginal på sidnumreringsbuffert
pageNumberStamp.BottomMargin = 10;

// Horisontell justering av sidnumreringsbufferten
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Startnummer för sidnumrering
pageNumberStamp.StartingNumber = 1;

// Ställ in sidnummerbufferttextegenskaper
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Ovanstående kod skapar en sidnummerstämpel med egenskaper som sidnummerformat, bottenmarginal, horisontell justering, startnummer och textegenskaper.

## Steg 4: Lägga till sidnummerstämpeln på en specifik sida

När sidnummerstämpeln är konfigurerad kan vi lägga till den på en specifik sida i PDF-dokumentet. Här är hur:

```csharp
// Lägg till sidnummerbufferten på en specifik sida
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Ovanstående kod lägger till sidnummerstämpeln på första sidan i PDF-dokumentet. Du kan ändra sidnumret efter behov.

## Steg 5: Spara det ändrade PDF-dokumentet

När sidnummerstämpeln har lagts till i PDF-dokumentet kan vi spara det ändrade PDF-dokumentet. Här är hur:

```csharp
// Spara det ändrade PDF-dokumentet
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där du vill spara det redigerade PDF-dokumentet.

### Exempel på källkod för sidnummerstämplar med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Skapa sidnummerstämpel
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Om stämpeln är bakgrund
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Ställ in textegenskaper
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Lägg till stämpel på en viss sida
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Spara utdatadokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till sidnummerstämplar i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu anpassa dina PDF-dokument genom att lägga till tydliga och informativa sidnummer.

### Vanliga frågor för sidnummerstämplar i PDF-fil

#### F: Vad är en sidnummerstämpel och hur används den för att lägga till sidnummer i en PDF-fil?

S: En sidnummerstämpel är en funktion i Aspose.PDF som låter dig lägga till dynamiska sidnummer på specifika sidor i ett PDF-dokument. I den här handledningen uppnås det genom att skapa ett PageNumberStamp-objekt, konfigurera dess egenskaper och lägga till det på en angiven sida.

#### F: Hur kan den medföljande C#-källkoden lägga till sidnummerstämplar i en PDF-fil?

S: Koden visar hur man laddar ett befintligt PDF-dokument, skapar en sidnummerstämpel, ställer in olika egenskaper (som format, teckensnitt, justering, etc.) och sedan lägger till stämpeln på en specifik sida. Stämpeln beräknar automatiskt det totala sidantal och infogar de korrekta sidnumren.

#### F: Kan jag anpassa utseendet på sidnumret, som typsnitt, färg och storlek?

S: Absolut, du kan anpassa utseendet på sidnummerstämpeln genom att justera egenskaper som teckensnitt, teckenstorlek, teckensnitt (fet, kursiv, etc.) och textfärg.

#### F: Är det möjligt att lägga till sidnummerstämplar på flera sidor i ett PDF-dokument?

S: Ja, du kan lägga till sidnummerstämplar på flera sidor genom att skapa flera PageNumberStamp-objekt och lägga till var och en på önskade sidor.

#### F: Kan jag välja om sidnummerstämpeln ska visas som en del av sidans innehåll eller som ett bakgrundselement?

 S: Ja, du kan styra om sidnummerstämpeln ska visas som en del av sidans innehåll eller som ett bakgrundselement genom att ställa in`Background` egenskapen för PageNumberStamp.

#### F: Hur anger jag formatet på sidnumret, inklusive det totala antalet sidor?

 S: Koden använder`Format`egenskapen för PageNumberStamp för att ange formatet för sidnumret. Makrot "# av" används för att representera det totala antalet sidor.

#### F: Vad händer om jag lägger till samma sidnummerstämpel på flera sidor?

S: Om du lägger till samma PageNumberStamp-instans på flera sidor visas rätt sidnummer för varje sida. Stämpeln justerar automatiskt sidnumret och det totala antalet sidor.

#### F: Kan jag lägga till sidnummerstämplar i sidhuvuds- eller sidfotsavsnitt i ett PDF-dokument?

S: Även om PageNumberStamps vanligtvis läggs till direkt i sidans innehåll, kan du använda FloatingBox eller andra tekniker för att placera dem i sidhuvuds- eller sidfotsavsnitt.

#### F: Hur anger jag positionen för sidnummerstämpeln på sidan?

 A: Den`BottomMargin` och`HorizontalAlignment` Egenskaperna för sidnummerstämpeln låter dig styra stämpelns position på sidan.

#### F: Vad händer om jag vill börja sidnumreringen från ett annat nummer istället för 1?

 S: Du kan ställa in`StartingNumber`egenskapen för PageNumberStamp för att ange startsidans nummer.