---
title: Lägg till lnk-anteckning
linktitle: Lägg till lnk-anteckning
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du lägger till funktionen Ink Annotation till PDF-dokument i C# med Aspose.PDF för .NET med steg-för-steg-guide och fullständig källkod.
type: docs
weight: 20
url: /sv/net/annotations/addlnkannotation/
---
Aspose.PDF för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att utföra olika PDF-operationer. En sådan operation är att lägga till Ink Annotation till PDF-dokument. I den här artikeln kommer vi att tillhandahålla en steg-för-steg-guide för att förklara C#-källkoden för att lägga till Ink Annotation med Aspose.PDF för .NET. Låt oss börja!

## Förstå bläckanteckningsfunktionen i Aspose.PDF för .NET

Innan vi dyker in i C#-källkoden, låt oss först förstå vad Ink Annotation är och dess användningsområden.

Ink Annotation är ett sätt att rita friformsbläckanteckningar på PDF-dokument. Det låter dig skapa kommentarer med en penna eller en mus. Den här funktionen är användbar i situationer där du behöver rita diagram, skisser eller andra typer av kommentarer.

## Steg 1: Skapa ett nytt dokument

Det första steget i att lägga till Ink Annotation i ett PDF-dokument är att skapa en ny instans av klassen Document. Detta uppnås med hjälp av följande kodavsnitt:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Här skapar vi en ny instans av klassen Document och lägger till en ny sida till den.

## Steg 2: Skapa bläckanteckning

Nästa steg är att skapa en instans av klassen InkAnnotation. Detta görs med hjälp av följande kodavsnitt:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Här skapar vi först en rektangel med klassen System.Drawing.Rectangle och konverterar den till Aspose.Pdf.Rectangle med metoden FromRect. Vi skapar sedan en instans av klassen InkAnnotation med hjälp av rektangeln, en lista med punkter och sidan där anteckningen läggs till.

Vi ställer sedan in olika egenskaper för InkAnnotation, såsom titel, färg, kepsstil, kant och opacitet. Slutligen lägger vi till anteckningen på sidan med metoden Annotations.Add.

## Steg 3: Spara dokumentet

Det sista steget är att spara PDF-dokumentet med bläckanteckningen tillagd. Detta uppnås med hjälp av följande kodavsnitt:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Här sammanfogar vi utdatafilens namn till datakatalogen och sparar dokumentet med hjälp av Spara-metoden.

### Exempel på källkod för att lägga till bläckanteckningar med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Spara utdatafil
doc.Save(dataDir);
```