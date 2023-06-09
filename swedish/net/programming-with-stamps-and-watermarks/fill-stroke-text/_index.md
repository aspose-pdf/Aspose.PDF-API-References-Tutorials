---
title: Fyll i strecktext
linktitle: Fyll i strecktext
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du enkelt fyller och beskriver text i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 90
url: /sv/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
I den här handledningen tar vi dig steg för steg om hur du fyller och beskriver text i ett PDF-dokument med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att tillämpa fyllnings- och konturfärger på text i PDF-dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Skapa TextState-objektet

Det första steget är att skapa ett TextState-objekt för att skicka de avancerade egenskaperna. Här är hur:

```csharp
// Skapa TextState-objekt för att överföra avancerade egenskaper
TextState ts = new TextState();

// Ställ in konturfärg
ts.StrokingColor = Color.Gray;

// Definiera textåtergivningsläget
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Ovanstående kod skapar ett nytt TextState-objekt och ställer in konturfärgen samt hur texten renderas.

## Steg 3: Laddar PDF-dokumentet

Nu när TextState-objektet är klart kan vi ladda PDF-dokumentet där vi vill använda textfyllningen och konturen. Här är hur:

```csharp
// Ladda PDF-dokumentet som indata
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Koden ovan laddar det befintliga PDF-dokumentet med klassen PdfFileStamp från Aspose.PDF.Facades-biblioteket.

## Steg 4: Lägg till fyllning och streck i text

Nu när PDF-dokumentet är laddat kan vi lägga till fyllningen och konturen till texten. Här är hur:

```csharp
// Skapa en stämpel (stämpel) med den definierade texten och egenskaperna
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Bind TextState-objektet
stamp.BindTextState(ts);

// Ange ursprung X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Lägg till stämpeln i dokumentet
fileStamp.AddStamp(stamp);
```

Ovanstående kod skapar en stämpel med den specificerade texten och definierade Fill och Stroke-egenskaper.

## Steg 5: Spara utdatadokumentet

När textstämpeln har lagts till kan vi spara det ändrade PDF-dokumentet. Här är hur:

```csharp
// Spara det ändrade dokumentet
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Ovanstående kod sparar det redigerade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för Fill Stroke Text med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Skapa TextState-objekt för att överföra avancerade egenskaper
TextState ts = new TextState();

// Ställ in färg för stroke
ts.StrokingColor = Color.Gray;

// Ställ in textåtergivningsläge
ts.RenderingMode = TextRenderingMode.StrokeText;

//Ladda ett inmatat PDF-dokument
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Bind TextState
stamp.BindTextState(ts);

// Ställ in X, Y ursprung
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Lägg till stämpel
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Slutsats

Grattis! Du har lärt dig hur du fyller och beskriver text i ett PDF-dokument med Aspose.PDF för .NET. Nu kan du tillämpa denna kunskap för att anpassa fyllnings- och konturfärger i dina PDF-dokument.
