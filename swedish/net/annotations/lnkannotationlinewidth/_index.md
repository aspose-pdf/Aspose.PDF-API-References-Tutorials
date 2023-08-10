---
title: lnk Annotation Line Width
linktitle: lnk Annotation Line Width
second_title: Aspose.PDF för .NET API Referens
description: Den här artikeln ger en steg-för-steg-guide för att ställa in linjebredden för lnk-anteckningen med Aspose.PDF för .NET.
type: docs
weight: 110
url: /sv/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF är ett kraftfullt och allmänt använt verktyg för att arbeta med PDF-filer i .NET-applikationer. Den tillhandahåller en mängd olika funktioner för att skapa, redigera och manipulera PDF-filer, inklusive möjligheten att lägga till kommentarer till sidor. I den här handledningen kommer vi att förklara hur man ställer in linjebredden för en länkkommentar med Aspose.PDF för .NET.

När du har dessa förutsättningar skapar du ett nytt konsolapplikationsprojekt i Visual Studio. Lägg sedan till en referens till Aspose.PDF för .NET-biblioteket genom att högerklicka på projektet i Solution Explorer, välja "Manage NuGet Packages" och söka efter "Aspose.PDF" i NuGet Package Manager.

För att lägga till en lnk-kommentar till ett PDF-dokument, följ dessa steg:

##  Steg 1: Skapa en ny`Document` object.
```csharp
Document doc = new Document();
```
## Steg 2: Lägg till en ny sida i dokumentet.
```csharp
doc.Pages.Add();
```
##  Steg 3: Skapa en lista över`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Steg 4: Skapa en ny`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Steg 5: Skapa en ny`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Steg 6: Lägg till gesten i listan över bläckgester.
```csharp
inkList.Add(gesture);
```
##  Steg 7: Skapa en ny`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Steg 8: Ställ in ämnet och rubriken för kommentaren.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Steg 9: Ställ in färgen på anteckningen.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Steg 10: Skapa en ny`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Steg 11: Lägg till anteckningen på sidan.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Steg 12: Spara dokumentet till en fil.
```csharp
// Spara utdatafil
doc.Save(dataDir);


```
### Exemplet visar lnk Annotation Line Width med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Spara utdatafil
doc.Save(dataDir);
```

## Slutsats

den här handledningen lärde vi oss hur man ställer in radbredden för en länkkommentar i ett PDF-dokument med Aspose.PDF för .NET. Aspose.PDF för .NET tillhandahåller ett brett utbud av verktyg och funktioner för att arbeta med PDF-dokument, inklusive möjligheten att skapa och anpassa länkkommentarer. Genom att följa den steg-för-steg-guide och använda den medföljande C#-källkoden, kan utvecklare enkelt lägga till interaktiva länkar till sina PDF-dokument, vilket förbättrar användarupplevelsen och interaktiviteten i sina applikationer. Aspose.PDF för .NET är ett mångsidigt bibliotek som ger .NET-utvecklare möjlighet att arbeta med PDF-filer effektivt och effektivt.

### FAQ's

#### F: Vad är en länkkommentar i ett PDF-dokument?

S: En länkkommentar i ett PDF-dokument är ett interaktivt element som låter dig skapa hyperlänkar eller åtgärder som leder användaren till en annan plats i samma dokument, en extern webbplats eller ett annat PDF-dokument.

#### F: Hur kan jag ställa in linjebredden för en länkanteckning med Aspose.PDF för .NET?

S: För att ställa in linjebredden för en länkkommentar med Aspose.PDF för .NET, kan du skapa en`InkAnnotation` objekt och ange egenskapen linjebredd.

#### F: Vilka egenskaper kan anpassas för en länkkommentar i Aspose.PDF för .NET?

S: Du kan anpassa olika egenskaper för en länkkommentar i Aspose.PDF för .NET, såsom dess plats, storlek, färg, kantegenskaper (bredd, stil, streckmönster och effekt), ämne, titel och synlighet.

#### F: Kan jag skapa en länkkommentar som innehåller flera bläckgester?

 S: Ja, du kan skapa en länkkommentar som innehåller flera bläckgester genom att lägga till flera`Point` matriser till`InkAnnotation` objekt.

#### F: Hur kan jag lägga till en länkkommentar till en specifik sida i PDF-dokumentet?

 S: För att lägga till en länkkommentar till en specifik sida i PDF-dokumentet måste du ange sidnumret när du skapar`InkAnnotation` objekt. Till exempel,`new InkAnnotation(doc.Pages[1], ...)` lägger till länkkommentaren på första sidan.