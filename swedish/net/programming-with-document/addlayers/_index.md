---
title: Lägg till lager
linktitle: Lägg till lager
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du lägger till lager i PDF-filer med Aspose.PDF för .NET. Steg-för-steg-guide med kodhandledning för att skapa och spara skiktade PDF-filer.
type: docs
weight: 20
url: /sv/net/programming-with-document/addlayers/
---

För att lägga till lager i en PDF-fil kommer vi att använda Aspose.PDF för .NET. Detta bibliotek låter oss arbeta med PDF-filer i .NET-applikationer effektivt. Följ steg-för-steg-instruktionerna nedan för att lägga till lager med Aspose.PDF för .NET.

## Steg 1: Skapa ett nytt PDF-dokument

 Börja med att skapa en ny instans av`Document`klass tillhandahållen av Aspose.PDF för .NET. Detta kommer att fungera som PDF-dokumentet där vi lägger till lagren.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Steg 2: Lägg till en sida i dokumentet

 Lägg sedan till en sida i dokumentet med hjälp av`Add` metod för`Pages` samling i`Document` klass.

```csharp
Page page = doc.Pages.Add();
```

## Steg 3: Skapa och lägg till lager på sidan

 Skapa instanser av`Layer` klass för varje lager du vill lägga till i PDF-filen. Ange en unik identifierare och ett namn för varje lager.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

I den här handledningen har vi lagt till tre lager med olika färger och namn på sidan.

## Steg 4: Spara PDF-filen

 Spara den ändrade PDF-filen med hjälp av`Save` metod för`Document` klass.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

Denna kod kommer att spara den modifierade PDF-filen i den angivna katalogen.

### Exempel på källkod för att lägga till lager till PDF-sidor med Aspose.PDF för .NET

```csharp            
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Slutsats

den här artikeln har vi tillhandahållit en steg-för-steg-guide för att lägga till lager i PDF-filer med Aspose.PDF för .NET. Genom att följa instruktionerna och använda de medföljande kodhandledningarna kan du enkelt infoga lager i dina PDF-dokument. Lager låter dig organisera och kontrollera innehållets synlighet, vilket ger en mer interaktiv och anpassningsbar upplevelse för dina användare.