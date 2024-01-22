---
title: Hämta dokumentfönstret
linktitle: Hämta dokumentfönstret
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du använder GetDocumentWindow-funktionen i Aspose.PDF för .NET för att hämta information om ett PDF-dokuments fönsteregenskaper.
type: docs
weight: 170
url: /sv/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF för .NET är ett kraftfullt PDF-manipuleringsbibliotek som låter utvecklare skapa, redigera och konvertera PDF-filer i sina .NET-applikationer. En av funktionerna som erbjuds av detta bibliotek är möjligheten att hämta information om ett dokuments fönsteregenskaper. Denna handledning guidar dig genom stegen för att använda`GetDocumentWindow` funktion i Aspose.PDF för .NET för att hämta information om ett PDF-dokuments fönsteregenskaper.

## Steg 1: Installera Aspose.PDF för .NET

 För att använda Aspose.PDF för .NET i dina .NET-applikationer måste du först installera biblioteket. Du kan ladda ner den senaste versionen av biblioteket från[Aspose.PDF för .NET nedladdningssida](https://releases.aspose.com/pdf/net).

När du har laddat ner biblioteket, extrahera innehållet i ZIP-filen till en mapp på din dator. Du måste sedan lägga till en referens till Aspose.PDF för .NET DLL i ditt .NET-projekt.

## Steg 2: Ladda PDF-dokumentet

När du har installerat Aspose.PDF för .NET och lagt till en referens till DLL-filen i ditt .NET-projekt kan du börja använda`GetDocumentWindow` funktion för att hämta information om ett PDF-dokuments fönsteregenskaper.

Det första steget i att använda den här funktionen är att ladda PDF-dokumentet som du vill hämta information om. För att göra detta kan du använda följande kod:

```csharp
// Sökvägen till PDF-dokumentet
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Öppna PDF-dokumentet
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 I koden ovan, ersätt`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där ditt PDF-dokument finns. Denna kod kommer att ladda PDF-dokumentet i en`Document` objekt, som du sedan kan använda för att hämta information om dokumentets fönsteregenskaper.

## Steg 3: Hämta dokumentets fönsteregenskaper

För att hämta information om ett PDF-dokuments fönsteregenskaper kan du använda följande kod:

```csharp
// Hämta dokumentets fönsteregenskaper
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

koden ovan hämtar varje rad en annan fönsteregenskap för PDF-dokumentet och matar ut den till konsolen. Du kan anpassa den här koden för att bara hämta de egenskaper som du är intresserad av.

### Exempel på källkod för hämta dokumentfönster för PDF-fil med Aspose.PDF för .NET 

 Här är den fullständiga källkoden för att hämta ett PDF-dokuments fönsteregenskaper med hjälp av`GetDocumentWindow` funktion i Aspose.PDF för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Få olika dokumentegenskaper
// Position för dokumentets fönster - Standard: falskt
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Övervägande läsordning; bestämmer sidans position
// När den visas sida vid sida - Standard: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Om fönstrets namnlist ska visa dokumentets titel
// Om falskt visar titelfältet PDF-filens namn - Standard: falskt
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Om storleken på dokumentets fönster ska anpassas till storleken på
// Första visade sidan - Standard: falskt
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Om menyraden för visningsprogrammet ska döljas - Standard: falskt
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Om verktygsfältet för visningsprogrammet ska döljas - Standard: falskt
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Om du vill dölja UI-element som rullningslister
// Och lämnar bara sidinnehållet visas - Standard: falskt
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Dokumentets sidläge. Så här visar du dokument när du avslutar helskärmsläge.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Sidlayouten dvs en sida, en kolumn
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Hur dokumentet ska visas när det öppnas
// Dvs visa miniatyrer, helskärm, visa bilaga panel
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Slutsats

I den här handledningen har vi lärt oss hur man använder Aspose.PDF för .NET för att hämta information om ett PDF-dokuments fönsteregenskaper. Genom att ladda ett PDF-dokument och komma åt dess fönsteregenskaper kan du samla information om hur dokumentet ska visas när det öppnas i ett visningsprogram. Aspose.PDF för .NET tillhandahåller en kraftfull uppsättning funktioner för att arbeta med PDF-filer programmatiskt, vilket gör det till ett värdefullt verktyg för PDF-manipulation i .NET-applikationer.

### FAQ's

#### F: Vad är syftet med att hämta ett PDF-dokuments fönsteregenskaper?

S: Genom att hämta ett PDF-dokuments fönsteregenskaper kan du samla information om hur PDF-dokumentet ska visas när det öppnas i ett visningsprogram. Dessa egenskaper styr olika aspekter som fönsterposition, visningsläge och synlighet för UI-element.

#### F: Hur kan jag installera Aspose.PDF för .NET i mitt .NET-projekt?

 S: För att installera Aspose.PDF för .NET måste du ladda ner biblioteket från[Aspose.PDF för .NET nedladdningssida](https://releases.aspose.com/pdf/net). Efter nedladdning, extrahera innehållet i ZIP-filen och lägg till en referens till Aspose.PDF för .NET DLL i ditt .NET-projekt.

#### F: Kan jag anpassa koden för att bara hämta specifika fönsteregenskaper?

S: Ja, du kan anpassa koden för att hämta specifika fönsteregenskaper genom att kommentera raderna som du inte behöver. Varje rad i koden motsvarar en specifik fönsteregenskap, så du kan inkludera eller exkludera egenskaper baserat på dina krav.

#### F: Vilka typer av fönsteregenskaper kan jag hämta med Aspose.PDF för .NET?

S: Med Aspose.PDF för .NET kan du hämta olika fönsteregenskaper för ett PDF-dokument, inklusive att centrera fönstret, ställa in sidlayouten, kontrollera visningen av verktygsfält och menyrader, med mera.