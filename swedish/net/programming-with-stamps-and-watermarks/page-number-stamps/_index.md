---
title: Sidnummerstämplar
linktitle: Sidnummerstämplar
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till sidnummerstämplar i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 160
url: /sv/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
den här handledningen guidar vi dig steg för steg om hur du lägger till sidnummerstämplar i ett PDF-dokument med Aspose.PDF för .NET. Vi använder den medföljande C#-källkoden för att öppna ett befintligt PDF-dokument, skapa en sidnummerstämpel, ställa in dess egenskaper och lägga till den på en specifik sida i PDF-dokumentet.

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
