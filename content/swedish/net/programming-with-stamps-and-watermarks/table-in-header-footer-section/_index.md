---
title: Tabell i sidhuvud
linktitle: Tabell i sidhuvud
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till en tabell i sidhuvudet/sidfoten i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 170
url: /sv/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
## Introduktion

Har du någonsin sett dig själv att stirra på ett vanligt PDF-dokument och önskat att det hade den där extra stilen? Nåväl, du har tur! Aspose.PDF för .NET låter dig skapa och manipulera PDF-filer som ett proffs. Idag dyker vi in i en praktisk funktion som låter dig lägga till en tabell i rubriken på ditt PDF-dokument. Du kommer inte bara att lära dig hur du gör det, utan jag kommer att guida dig steg-för-steg, vilket gör hela processen lika smidig som smör. 🎉

## Förutsättningar

Innan vi hoppar in i själva kodningsdelen, låt oss se till att du har allt du behöver för att komma igång. Här är vad du behöver:

1.  Visual Studio: Se till att du har Visual Studio installerat på din dator. Om du inte har det kan du ladda ner den från[Microsofts webbplats](https://visualstudio.microsoft.com/).
2.  Aspose.PDF-bibliotek: Du måste ha Aspose.PDF-biblioteket för .NET. Du kan använda följande länk för att få[Aspose.PDF för .NET-paket](https://releases.aspose.com/pdf/net/).
3. Grundläggande kunskaper i C#: Du bör ha åtminstone en grundläggande förståelse för C#. Oroa dig inte om du fortfarande lär dig; Jag ska hålla det så enkelt som möjligt!

## Importera paket

Okej, dags att kavla upp ärmarna och börja koda! Men först måste vi ställa in vår miljö genom att importera nödvändiga paket. Så här gör du:

###  Öppna ditt projekt
Öppna ditt Visual Studio-projekt där du kommer att arbeta med att skapa PDF. 

###  Lägg till referens till Aspose.PDF
1. NuGet Package Manager: Högerklicka på ditt projekt i Solution Explorer och välj "Manage NuGet Packages".
2. Sök efter Aspose.PDF: I sökfältet, skriv "Aspose.PDF" och installera paketet.

I slutet av detta steg bör du ha allt inställt och redo att börja koda!

Nu, låt oss smutsa ner händerna med lite kod! Följ dessa steg för att skapa en tabell i rubriken i din PDF:

## Steg 1: Ställ in sökvägen till din dokumentkatalog

Innan vi börjar skapa vår PDF måste vi definiera var vårt dokument ska lagras. Så här gör du:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ändra detta till din faktiska katalog
```

 Ersätta`YOUR DOCUMENT DIRECTORY`med sökvägen där du vill spara din PDF. Det här kan vara var som helst på ditt system – se bara till att det är tillgängligt!

## Steg 2: Instantiera dokumentet

Därefter skapar vi ett nytt PDF-dokument.

```csharp
// Instantiera Document-instansen genom att anropa den tomma konstruktorn
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();
```

Det vi gör här är att skapa ett tomt PDF-dokument där vi lägger till alla våra godsaker.

## Steg 3: Skapa en ny sida

Låt oss lägga till en ny sida i vårt dokument. 

```csharp
// Skapa en sida i pdf-dokumentet
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Se den här sidan som en tom duk där vi målar vårt mästerverk!

## Steg 4: Skapa en rubriksektion

Nu ska vi skapa en rubrik för vår PDF.

```csharp
// Skapa en rubriksektion av PDF-filen
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
```

Denna rubrik kommer att hålla vårt bord. 

## Steg 5: Tilldela sidhuvudet till sidan

Därefter vill vi se till att vår rubrik visas på sidan.

```csharp
// Ställ in udda rubrik för PDF-filen
page.Header = header;
```

## Steg 6: Ställ in den övre marginalen

Låt oss justera marginalen för att se till att vår header har lite andrum överst.

```csharp
//Ställ in den övre marginalen för rubriksektionen
header.Margin.Top = 20;
```

Att sätta en marginal är som att ge din text ett personligt utrymme – ingen gillar att vara trång!

## Steg 7: Skapa tabellen

Nu är det dags att skapa tabellen som kommer in i vår rubrik.

```csharp
// Instantiera ett tabellobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Steg 8: Lägg till tabellen i rubriken

Vi lägger till vår nyskapade tabell i rubrikens styckesamling.

```csharp
// Lägg till tabellen i styckesamlingen av önskat avsnitt
header.Paragraphs.Add(tab1);
```

## Steg 9: Ställ in cellgränser

Låt oss ge vår tabell lite struktur genom att definiera standardcellgränsen.

```csharp
// Ställ in standardcellkant med BorderInfo-objekt
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Steg 10: Definiera kolumnbredder

Du kan ange hur bred varje kolumn i tabellen ska vara.

```csharp
// Ställ in med tabellens kolumnbredder
tab1.ColumnWidths = "60 300";
```

Värdena representerar bredden på varje kolumn i punkter. Justera dem gärna för att passa dina behov!

## Steg 11: Skapa rader och lägg till celler

Det är dags att kasta in några rader och celler! 

```csharp
//Skapa rader i tabellen och sedan celler i raderna
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;
```

Detta skapar den första raden med en cell som innehåller text och ställer in dess bakgrundsfärg till grå.

## Steg 12: Ställ in radspann och textstil

Vill du att din rad ska sträcka sig över flera kolumner? Så här gör du:

```csharp
// Ställ in radintervallvärdet för första raden som 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

Det här steget ställer inte bara in radintervallet utan ändrar också textfärg och teckensnitt.

## Steg 13: Lägg till en andra rad

Låt oss lägga till ytterligare en rad i vårt bord, eller hur?

```csharp
// Skapa ytterligare en rad i tabellen
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Ställ in bakgrundsfärgen för Row2
row2.BackgroundColor = Color.White;
```

## Steg 14: Lägg till en bild på den andra raden

Nu ska vi slänga in en logotyp för att få vårt bord att se snyggt ut!

```csharp
// Lägg till cellen som innehåller bilden
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg"; // Se till att du placerar bilden i din katalog
```

 Glöm inte att byta ut`"aspose-logo.jpg"` med det faktiska namnet på din bild!

## Steg 15: Justera bildbredden

Ställ in bildens bredd för att säkerställa att den ser rätt ut i cellen.

```csharp
// Ställ in bildens bredd till 60
img.FixWidth = 60;

//Lägg till bilden i tabellcellen
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
cell2.Paragraphs.Add(img);
```

## Steg 16: Lägg till text i den andra cellen

Dags att lägga till lite text bredvid vår logotyp!

```csharp
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

## Steg 17: Justera texten vertikalt och horisontellt

Se till att allt ser snyggt ut. Justera din text!

```csharp
// Ställ in den vertikala justeringen av texten som mittjusterad
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Steg 18: Spara PDF-dokumentet

Sist men inte minst, låt oss rädda vår skapelse!

```csharp
// Spara pdf-filen
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Och voilà! Du har skapat en fantastisk PDF komplett med en tabell i rubriken!

## Slutsats

Och där har du det! Du har framgångsrikt lagt till en tabell i rubriken på ditt PDF-dokument med Aspose.PDF för .NET. Det är otroligt hur bara några rader kod kan förvandla en enkel PDF till ett proffsigt dokument. Oavsett om du förbereder rapporter, fakturor eller presentationer, kan lägga till en touch av kreativitet göra hela skillnaden. 

## FAQ's

### Vad är Aspose.PDF för .NET?
Aspose.PDF för .NET är ett kraftfullt bibliotek som låter utvecklare skapa och manipulera PDF-dokument programmatiskt.

### Behöver jag en licens för att använda Aspose.PDF?
 Även om du kan använda biblioteket gratis under provperioden, krävs en licens för utökad användning. Du kan få en[tillfällig licens](https://purchase.aspose.com/temporary-license/) för utvärdering.

### Var kan jag hitta dokumentationen?
Du kan hitta omfattande dokumentation och exempel på[Aspose.PDF dokumentationssida](https://reference.aspose.com/pdf/net/).

### Hur kan jag kontakta support för tekniska problem?
 Du kan nå ut för stöd genom[Aspose forum](https://forum.aspose.com/c/pdf/10).

### Kan jag skapa tabeller i andra delar av PDF-filen?
Absolut! Du kan också skapa tabeller i sidfötter och kroppssektioner; följ bara liknande steg.