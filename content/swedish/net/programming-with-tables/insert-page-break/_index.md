---
title: Infoga sidbrytning i PDF-fil
linktitle: Infoga sidbrytning i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du infogar en sidbrytning i PDF-filen med Aspose.PDF för .NET.
type: docs
weight: 110
url: /sv/net/programming-with-tables/insert-page-break/
---
I den här handledningen kommer vi att lära oss hur man infogar en sidbrytning i PDF-filen med Aspose.PDF för .NET. Vi kommer att förklara källkoden i C# steg för steg. I slutet av denna handledning kommer du att veta hur du lägger till en sidbrytning efter ett visst antal rader i en tabell i ett PDF-dokument. Låt oss börja!

## Steg 1: Sätta upp miljön
Se till att du har konfigurerat din C#-utvecklingsmiljö med Aspose.PDF för .NET. Lägg till referensen till biblioteket och importera de nödvändiga namnrymden.

## Steg 2: Skapa dokumentet och tabellen
Vi skapar en ny dokumentinstans och lägger till en sida i detta dokument. Därefter skapar vi en tabellinstans för att representera vår tabell i PDF-dokumentet. Vi definierar också kantstilarna för tabellen.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Steg 3: Lägg till rader i tabellen
Vi använder en slinga för att lägga till 200 rader till arrayen. För varje rad skapar vi en instans av Row och lägger till två celler med textinnehåll.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // När 10 rader läggs till lägger vi in en ny sidbrytning
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Steg 4: Lägga till tabellen i dokumentet
Vi lägger till tabellen i styckesamlingen på dokumentsidan.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Steg 5: Spara dokumentet
Vi sparar PDF-dokumentet med sidbrytningen inlagd.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Exempel på källkod för Insert Page Break med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera dokumentinstans
Document doc = new Document();
// Lägg till sida till sidor samling av PDF-fil
doc.Pages.Add();
// Skapa tabellinstans
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Ställ in kantstil för bordet
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Ställ in standard kantstil för tabell med kantfärg som röd
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Ange bredd för tabellkolumner
tab.ColumnWidths = "100 100";
// Skapa en slinga för att lägga till 200 rader för tabell
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// När 10 rader har lagts till, rendera ny rad på ny sida
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Lägg till tabell till styckesamling av PDF-fil
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Spara PDF-dokumentet
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Slutsats
I den här handledningen lärde vi oss hur man infogar en sidbrytning i ett PDF-dokument med Aspose.PDF för .NET. Du kan använda den här steg-för-steg-guiden för att lägga till en sidbrytning efter ett visst antal rader i en tabell i ett PDF-dokument med C#.

### Vanliga frågor för att infoga sidbrytning i PDF-fil

#### F: Hur kan jag ändra sidstorleken för de nya sidorna som skapats efter sidbrytningen?

 S: För att ändra sidstorleken för de nya sidorna som skapats efter sidbrytningen kan du ställa in`PageSize` egendom av`Page` objekt. Du kan till exempel använda följande kod för att ställa in sidstorleken till A4:

```csharp
// Ställ in sidstorleken till A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### F: Kan jag kontrollera sidmarginalerna för de nya sidorna efter sidbrytningen?

 S: Ja, du kan styra sidmarginalerna för de nya sidorna efter sidbrytningen. Använd`Margin` egendom av`Page` objekt för att ställa in sidmarginalerna. Till exempel, för att ställa in alla marginaler till 10 poäng, kan du använda följande kod:

```csharp
// Ställ in alla marginaler till 10 poäng
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### F: Är det möjligt att lägga till sidhuvuden och sidfötter på de nya sidorna efter sidbrytningen?

 S: Ja, du kan lägga till sidhuvuden och sidfötter på de nya sidorna efter sidbrytningen. Använd`Page.Header` och`Page.Footer` egenskaper för att lägga till innehåll i sidhuvudet och sidfoten på sidan. Till exempel:

```csharp
// Lägg till rubrik på de nya sidorna
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Lägg till sidfot på de nya sidorna
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### F: Kan jag infoga sidbrytningar på specifika platser andra än efter ett visst antal rader?

 S: Ja, du kan infoga sidbrytningar på specifika platser andra än efter ett visst antal rader. Du kan ställa in`IsInNewPage` egenskap hos en rad till`true` för att tvinga tabellen att starta en ny sida efter den raden.

#### F: Hur kan jag justera sidbrytningsbeteendet baserat på innehållets höjd?

S: Du kan använda`IsBroken` egenskapen för tabellen för att aktivera eller inaktivera automatisk radbrytning över sidor. När inställd på`true`, gör det att rader kan delas över sidor baserat på innehållets höjd.