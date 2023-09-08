---
title: Lägg till textkant i PDF-fil
linktitle: Lägg till textkant i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till en textram i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 70
url: /sv/net/programming-with-text/add-text-border/
---
Denna handledning guidar dig genom processen att lägga till en textram i PDF-fil med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

## Krav
Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan C#-kompilator installerad på din maskin.
- Aspose.PDF för .NET-bibliotek. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda en pakethanterare som NuGet för att installera den.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnrymder
I kodfilen där du vill lägga till textkanten, lägg till följande med hjälp av direktivet överst i filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Steg 3: Ställ in dokumentkatalogen
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Skapa ett nytt dokumentobjekt
 Instantiera en ny`Document` objekt genom att lägga till följande kodrad:

```csharp
Document pdfDocument = new Document();
```

## Steg 5: Lägg till en sida i dokumentet
 Lägg till en ny sida i dokumentet med hjälp av`Add` metod för`Pages`samling. I den angivna koden är den nya sidan tilldelad variabeln`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Steg 6: Skapa ett TextFragment
 Skapa en`TextFragment` objekt och ge önskad text. Ställ in positionen för textfragmentet med hjälp av`Position` fast egendom. I den medföljande koden är texten inställd på "huvudtext" och placerad vid (100, 600) på sidan.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Steg 7: Ställ in textegenskaper
Anpassa textegenskaperna som teckenstorlek, typsnitt, bakgrundsfärg, förgrundsfärg etc. I den medföljande koden ställs egenskaper som teckenstorlek, teckensnitt, bakgrundsfärg, förgrundsfärg och streckfärg in för textfragmentet.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Steg 8: Aktivera textkant
 För att aktivera textramen, ställ in`DrawTextRectangleBorder`egenskapen hos textfragmentet`TextState` till`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Steg 9: Lägg till TextFragment på sidan
 Använd`TextBuilder` klass för att lägga till`TextFragment` invända mot sidan.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Steg 10: Spara PDF-dokumentet
 Spara PDF-dokumentet med hjälp av`Save` metod för`Document` objekt. Ange sökvägen till utdatafilen som du ställde in i steg 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Exempel på källkod för Add Text Border med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Skapa nytt dokumentobjekt
Document pdfDocument = new Document();
// Skaffa en speciell sida
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Skapa textfragment
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Ställ in textegenskaper
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Ställ in StrokingColor-egenskapen för att rita en ram (stryka) runt textrektangeln
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Ställ in egenskapsvärdet för DrawTextRectangleBorder till true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Spara dokumentet
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Slutsats
Du har framgångsrikt lagt till en textram till ditt PDF-dokument med Aspose.PDF för .NET. Den resulterande PDF-filen kan nu hittas på den angivna sökvägen för utdatafilen.

### FAQ's

#### F: Vad är huvudfokus för denna handledning?

S: Denna handledning guidar dig genom processen att lägga till en textram till en PDF-fil med Aspose.PDF för .NET-biblioteket. Den medföljande C#-källkoden visar de nödvändiga stegen för att uppnå detta.

#### F: Vilka namnutrymmen behöver jag importera för den här handledningen?

S: I kodfilen där du vill lägga till textkanten, importera följande namnområden i början av filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### F: Hur anger jag dokumentkatalogen?

 S: Lokalisera raden i koden`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

#### F: Hur skapar jag ett dokumentobjekt?

 S: I steg 4 kommer du att instansiera en ny`Document` objekt med följande kodrad:

```csharp
Document pdfDocument = new Document();
```

#### F: Hur lägger jag till en sida i dokumentet?

 S: I steg 5 lägger du till en ny sida i dokumentet med hjälp av`Add` metod för`Pages` samling:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### F: Hur skapar jag ett TextFragment och ställer in dess position?

 S: I steg 6 skapar du en`TextFragment`objekt och ställ in dess position på sidan med hjälp av`Position` fast egendom:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### F: Hur kan jag anpassa textegenskaperna, inklusive textkanten?

S: I steg 7 kommer du att anpassa olika textegenskaper som teckenstorlek, teckensnitt, bakgrundsfärg, förgrundsfärg och textkant:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### F: Hur lägger jag till TextFragment i PDF-dokumentet?

 S: I steg 9 kommer du att använda`TextBuilder` klass för att lägga till`TextFragment` invända mot sidan:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### F: Hur sparar jag det resulterande PDF-dokumentet?

 S: När du har lagt till texten med en ram, använd`Save` metod för`Document` objekt för att spara PDF-dokumentet:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### F: Vad är det viktigaste med den här handledningen?

S: Genom att följa den här handledningen har du framgångsrikt lärt dig hur du förbättrar ditt PDF-dokument genom att lägga till en textram med Aspose.PDF för .NET. Detta kan vara särskilt användbart för att betona specifikt textinnehåll i dina PDF-filer.