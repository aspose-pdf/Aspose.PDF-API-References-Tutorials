---
title: Lägg till efterföljande rader indrag
linktitle: Lägg till efterföljande rader indrag
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till efterföljande rader indrag i text med Aspose.PDF för .NET.
type: docs
weight: 60
url: /sv/net/programming-with-text/add-subsequent-lines-indent/
---

Denna handledning guidar dig genom processen att lägga till efterföljande rader indrag i text med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

## Krav
Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan C#-kompilator installerad på din maskin.
- Aspose.PDF för .NET-bibliotek. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda en pakethanterare som NuGet för att installera den.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnrymder
I kodfilen där du vill lägga till efterföljande radindrag, lägg till följande med hjälp av direktivet överst i filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Steg 3: Ställ in dokumentkatalogen
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Skapa ett nytt dokumentobjekt
 Instantiera en ny`Document` objekt genom att lägga till följande kodrad:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Steg 5: Lägg till en sida i dokumentet
 Lägg till en ny sida i dokumentet med hjälp av`Add` metod för`Pages` samling. I den angivna koden är den nya sidan tilldelad variabeln`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Steg 6: Skapa ett TextFragment med efterföljande rader indrag
 Instantiera en`TextFragment` objekt och ge önskad text. I den angivna koden är texten tilldelad variabeln`text` . Initiera sedan`TextFormattingOptions` för`TextFragment` och specificera`SubsequentLinesIndent` värde.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Steg 7: Lägg till TextFragment på sidan
 Lägg till`TextFragment` invända mot styckesamlingen på sidan.

```csharp
page.Paragraphs.Add(text);
```

## Steg 8: Upprepa steg 6 och 7 för ytterligare rader
För att lägga till efterföljande rader med samma indrag, upprepa steg 6 och 7 för varje rad. Uppdatera textinnehållet vid behov.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Steg 9: Spara PDF-dokumentet
 Spara PDF-dokumentet med hjälp av`Save` metod för`Document` objekt. Ange sökvägen till utdatafilen.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Exempel på källkod för Lägg till efterföljande rader indrag med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Skapa nytt dokumentobjekt
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Initiera TextFormattingOptions för textfragmentet och ange SubsequentLinesIndent-värdet
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Slutsats
Du har framgångsrikt lagt till efterföljande rader indrag i text med Aspose.PDF för .NET. Den resulterande PDF-filen kan nu hittas på den angivna sökvägen för utdatafilen.