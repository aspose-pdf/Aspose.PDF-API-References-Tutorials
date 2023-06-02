---
title: Skapa flerskikts PDF First Approach
linktitle: Skapa flerskikts PDF First Approach
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du skapar PDF-dokument i flera lager med hjälp av First Approach med Aspose.PDF för .NET. Lägg till text, bilder och mer för att förbättra dina PDF-filer.
type: docs
weight: 70
url: /sv/net/programming-with-document/createmultilayerpdffirstapproach/
---

I den här handledningen kommer vi att guida dig genom processen att skapa en PDF med flera lager med den första metoden med Aspose.PDF för .NET. Detta tillvägagångssätt låter dig lägga till flera lager i ditt PDF-dokument. Följ steg-för-steg-guiden nedan:

## Steg 1: Initiera PDF-dokumentet

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## Steg 2: Lägg till en ny sida i dokumentet

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## Steg 3: Lägg till ett textfragment på sidan

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## Steg 4: Anpassa textfragmentet

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## Steg 5: Lägg till en bild på sidan

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## Steg 6: Lägg till en flytande ruta på sidan

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## Steg 7: Spara det resulterande PDF-dokumentet

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Grattis! Du har framgångsrikt skapat ett PDF-dokument med flera lager med den första metoden med Aspose.PDF för .NET.

### Exempel på källkod för Create Multilayer PDF First Approach med Aspose.PDF för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);

t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;

Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);

pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Nu kan du skapa PDF-dokument i flera lager med den första metoden med Aspose.PDF för .NET.
