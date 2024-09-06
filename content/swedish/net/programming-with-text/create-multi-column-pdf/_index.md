---
title: Skapa flera kolumner pdf
linktitle: Skapa flera kolumner pdf
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du skapar en PDF med flera kolumner med Aspose.PDF för .NET.
type: docs
weight: 110
url: /sv/net/programming-with-text/create-multi-column-pdf/
---
Denna handledning guidar dig genom processen att skapa en PDF med flera kolumner med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

## Krav
Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan C#-kompilator installerad på din maskin.
- Aspose.PDF för .NET-bibliotek. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda en pakethanterare som NuGet för att installera den.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnrymder
I kodfilen där du vill skapa en PDF med flera kolumner, lägg till följande med hjälp av direktiv överst i filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Steg 3: Ställ in dokumentkatalogen
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Skapa en ny dokumentinstans
 Instantiera en ny`Document` objekt genom att lägga till följande kodrad:

```csharp
Document doc = new Document();
```

## Steg 5: Ställ in sidmarginalerna
 Ange information om vänster och höger marginal för PDF-filen med hjälp av`PageInfo.Margin` egendom av`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Steg 6: Lägg till en sida i dokumentet
 Lägg till en ny sida i dokumentet med hjälp av`Add` metod för`Pages`samling. I den angivna koden är den nya sidan tilldelad variabeln`page`.

```csharp
Page page = doc.Pages.Add();
```

## Steg 7: Skapa ett grafobjekt och lägg till en linje
 Skapa en ny`Graph` objekt med specifika dimensioner och lägg till en linje till det. Lägg sedan till`Graph` invända mot`Paragraphs` samling av sidan.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Steg 8: Lägg till rubriktext med HTML-formatering
 Skapa en`HtmlFragment` objekt och ställ in dess innehåll till önskad HTML-text. Lägg sedan till fragmentet i`Paragraphs` samling av sidan.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Steg 9: Skapa en FloatingBox med flera kolumner
 Skapa en`FloatingBox` objekt och ställ in antalet kolumner och kolumnavstånd. Lägg sedan till textfragment och en rad till`Paragraphs` samling av`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Steg 10: Spara PDF-dokumentet
 Spara PDF-dokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir);
```

### Exempel på källkod för Skapa Multi Column Pdf med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//Ange information om vänstermarginalen för PDF-filen
doc.PageInfo.Margin.Left = 40;
// Ange information om högermarginalen för PDF-filen
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Lägg till raden i parafrassamlingen av sektionsobjektet
page.Paragraphs.Add(graph1);
// Ange koordinaterna för linjen
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Skapa strängvariabler med text som innehåller html-taggar
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Skapa textstycken som innehåller HTML-text
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Lägg till fyra kolumner i avsnittet
box.ColumnInfo.ColumnCount = 2;
// Ställ in avståndet mellan kolumnerna
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Skapa ett grafobjekt för att rita en linje
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Ange koordinaterna för linjen
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Lägg till raden i styckesamlingen av sektionsobjekt
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Spara PDF-fil
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Slutsats
Du har framgångsrikt skapat en PDF med flera kolumner med Aspose.PDF för .NET. Den resulterande PDF-filen kan nu hittas på den angivna sökvägen för utdatafilen.

### FAQ's

#### F: Vad är fokus för denna handledning?

Den här handledningen är inriktad på att guida dig genom processen att skapa en PDF med flera kolumner med Aspose.PDF för .NET-biblioteket. Den medföljande C#-källkoden visar de nödvändiga stegen för att uppnå detta.

#### F: Vilka namnområden ska jag importera för den här handledningen?

S: I kodfilen där du vill skapa en PDF med flera kolumner, importera följande namnområden i början av filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### F: Hur anger jag dokumentkatalogen?

 S: Hitta raden i koden`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

#### F: Hur skapar jag en ny dokumentinstans?

 S: I steg 4 kommer du att instansiera en ny`Document` objekt med den medföljande koden.

#### F: Hur ställer jag in sidmarginalerna?

 S: I steg 5 kommer du att använda`PageInfo.Margin` egendom av`Document` för att ange information om vänster och höger marginal för PDF-filen.

#### F: Hur lägger jag till en sida i dokumentet?

 S: I steg 6 lägger du till en ny sida i dokumentet med hjälp av`Add` metod för`Pages` samling.

#### F: Hur skapar jag ett Graph-objekt och lägger till en linje?

 S: I steg 7 skapar du en ny`Graph` objekt, lägg till en rad i det och lägg sedan till`Graph` invända mot`Paragraphs` samling av sidan.

#### F: Hur lägger jag till rubriktext med HTML-formatering?

 S: I steg 8 skapar du en`HtmlFragment` objekt och ställ in dess innehåll till önskad HTML-text, lägg sedan till fragmentet i`Paragraphs` samling av sidan.

#### F: Hur skapar jag en FloatingBox med flera kolumner?

 S: I steg 9 skapar du en`FloatingBox` objekt med flera kolumner och kolumnavstånd, lägg sedan till textfragment och en rad i`Paragraphs` samling av`FloatingBox`.

#### F: Hur sparar jag PDF-dokumentet?

 S: I steg 10 sparar du PDF-dokumentet med hjälp av`Save` metod för`Document` objekt.

#### F: Vad är det viktigaste med den här handledningen?

S: Genom att följa den här handledningen har du lärt dig hur du skapar ett PDF-dokument med flera kolumner med Aspose.PDF för .NET. Detta kan vara användbart för att visa innehåll i en strukturerad och organiserad layout.