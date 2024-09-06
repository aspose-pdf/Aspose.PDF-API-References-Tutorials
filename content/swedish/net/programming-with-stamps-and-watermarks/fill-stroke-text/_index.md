---
title: Fyll strecktext i PDF-fil
linktitle: Fyll strecktext i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du enkelt fyller och beskriver text i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 90
url: /sv/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
den här handledningen tar vi dig steg för steg om hur du fyller och beskriver text i PDF-fil med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att applicera fyllnings- och konturfärger på text i PDF-filen.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Skapa TextState-objektet

Det första steget är att skapa ett TextState-objekt för att skicka de avancerade egenskaperna. Så här gör du:

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

Nu när TextState-objektet är klart kan vi ladda PDF-dokumentet där vi vill använda textfyllningen och konturen. Så här gör du:

```csharp
// Ladda PDF-dokumentet som indata
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Koden ovan laddar det befintliga PDF-dokumentet med klassen PdfFileStamp från Aspose.PDF.Facades-biblioteket.

## Steg 4: Lägg till fyllning och streck i text

Nu när PDF-dokumentet är laddat kan vi lägga till fyllningen och konturen till texten. Så här gör du:

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

När textstämpeln har lagts till kan vi spara det ändrade PDF-dokumentet. Så här gör du:

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

// Ladda ett inmatat PDF-dokument
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

### Vanliga frågor om fyllningslinjetext i PDF-fil

#### F: Vad innebär det att fylla och konturera text i ett PDF-dokument, och när kan jag behöva göra det?

S: Att fylla och konturera text i ett PDF-dokument innebär att färger appliceras på det inre av texttecken (fyll) och på kanterna runt texten (kontur). Detta kan användas för att förbättra det visuella utseendet på texten, skapa betoning eller markera specifikt innehåll i PDF:en.

#### F: Hur fyller den medföljande C#-källkoden ut text i en PDF-fil?

 S: Den medföljande källkoden visar hur man skapar en`TextState` objekt för att definiera avancerade textegenskaper, såsom konturfärg och renderingsläge. Den använder sedan Aspose.PDF.Facades för att ladda ett befintligt PDF-dokument, skapa en stämpel som innehåller texten med specificerade fyllnings- och linjeegenskaper och lägga till stämpeln i dokumentet.

####  F: Vad är syftet med`TextState` object in the code?

 A: Den`TextState`objekt används för att definiera avancerade textegenskaper, inklusive färgen på textkonturen (strecken) och renderingsläget. Det låter dig anpassa hur texten ser ut i form av streck och fyllning.

#### F: Kan jag använda olika fyllnings- och konturfärger på olika delar av samma text?

 S: Ja, du kan ändra koden för att skapa en annan`TextState` objekt med distinkta fyllnings- och konturfärger och applicera dem på specifika delar av texten med separata`Stamp` föremål.

#### F: Kan jag använda fyllnings- och konturfärger på text som redan finns i PDF-dokumentet?

 S: Ja, du kan använda liknande principer för att tillämpa fyllnings- och konturfärger på befintlig text i PDF-dokumentet genom att välja lämpliga textobjekt och lägga till dem som stämplar med önskat`TextState` fastigheter.

#### F: Hur kan jag justera opaciteten och blandningen av den fyllda och konturerade texten?

 S: Den medföljande koden låter dig ställa in opacitet och blandningsegenskaper för stämpeln med hjälp av`Opacity` och`BlendingSpace`respektive fastigheter. Du kan justera dessa värden för att uppnå önskad visuell effekt.

#### F: Hur kan jag använda olika fyllnings- och konturfärger på flera stämplar i samma PDF-dokument?

 S: Du kan skapa flera`TextState` objekt med olika fyllnings- och konturfärger och skapa sedan separata`Stamp` objekt för varje uppsättning text med distinkta färger. Lägg till dessa stämplar i samma PDF-dokument med hjälp av`PdfFileStamp` klass.

#### F: Kan jag använda andra typsnitt än Arial för den konturerade och fyllda texten?

 S: Ja, du kan ändra teckensnittet genom att ändra teckensnittsnamnsparametern i`FormattedText` konstruktör när du skapar stämpeln. Du kan använda alla teckensnitt som är tillgängliga på ditt system.

#### F: Hur kan jag ändra rotationsvinkeln för den konturerade och fyllda texten?

 S: Den medföljande koden låter dig ställa in stämpelns rotationsvinkel med hjälp av`Rotation` egendom. Du kan justera den här egenskapen för att ange önskad rotationsvinkel för texten.

#### F: Hur kan jag kontrollera placeringen och storleken på den konturerade och fyllda texten på sidan?

 S: Du kan använda`SetOrigin` metod för`Stamp` objekt för att ställa in X- och Y-koordinaterna för stämpelns position på sidan. Dessutom kan du justera teckenstorleken i`FormattedText` konstruktor för att kontrollera storleken på texten.