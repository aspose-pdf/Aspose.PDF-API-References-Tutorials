---
title: Skapa flerskikts PDF Second Approach
linktitle: Skapa flerskikts PDF Second Approach
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du skapar en PDF med flera lager med Aspose.PDF för .NET. Steg-för-steg-guide med källkod för att skapa dynamiska PDF-filer med text och bilder.
type: docs
weight: 80
url: /sv/net/programming-with-document/createmultilayerpdfsecondapproach/
---

den här handledningen kommer vi att utforska hur man skapar en PDF med flera lager med den andra metoden i Aspose.PDF för .NET. Vi kommer att tillhandahålla en steg-för-steg-guide med detaljerade förklaringar och inkludera hela källkoden. Genom att följa denna handledning kommer du att kunna generera PDF-dokument med flera lager med hjälp av Aspose.PDF-biblioteket i dina .NET-applikationer.

Låt oss nu komma igång med steg-för-steg-guiden.

## Steg 1: Ställ in miljön

Till att börja med, öppna Visual Studio och skapa ett nytt C#-projekt. Se till att du har refererat till Aspose.PDF-biblioteket i ditt projekt. När du har konfigurerat miljön är du redo att gå vidare till nästa steg.

## Steg 2: Initiera variabler

I detta steg kommer vi att initiera de nödvändiga variablerna. Vi måste ställa in sökvägen till dokumentkatalogen och definiera färgvariabler för PDF-lagren. Här är kodavsnittet:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## Steg 3: Skapa ett PDF-dokument

Därefter kommer vi att skapa en ny instans av klassen Aspose.Pdf.Document, som representerar ett PDF-dokument. Här är kodavsnittet:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Steg 4: Lägg till en sida i dokumentet

I det här steget kommer vi att lägga till en ny sida i PDF-dokumentet. Här är kodavsnittet:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Steg 5: Lägg till text på sidan

Nu lägger vi till ett textfragment på sidan. Texten kommer att visas som ett stycke 3-segment med en röd färg. Här är kodavsnittet:

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## Steg 6: Lägg till en bild på sidan

I det här steget kommer vi att lägga till en bild på sidan. Bilden kommer att placeras som en flytande låda med en viss storlek. Här är kodavsnittet:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## Steg 7: Spara PDF-filen

I det här steget kommer vi att spara PDF-filen till en fil.

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### Exempel på källkod för att skapa flerskikts PDF, andra tillvägagångssätt med Aspose.PDF för .NET.

```csharp

            
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
            
        
```

## Slutsats

den här artikeln har vi lärt oss hur man skapar en PDF med flera lager med den andra metoden av Aspose.PDF för .NET. Vi har försett dig med steg-för-steg-instruktioner och den fullständiga källkoden som krävs för att skapa en PDF med flera lager.