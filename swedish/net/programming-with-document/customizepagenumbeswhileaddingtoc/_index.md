---
title: Anpassa sidnummer när du lägger till innehållsförteckning
linktitle: Anpassa sidnummer när du lägger till innehållsförteckning
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du anpassar sidnummer samtidigt som du lägger till en innehållsförteckning (TOC) med Aspose.PDF för .NET med denna steg-för-steg-guide och kodexempel.
type: docs
weight: 100
url: /sv/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---

I den här handledningen kommer vi att utforska hur man anpassar sidnummer samtidigt som man lägger till en innehållsförteckning (TOC) med Aspose.PDF för .NET. Vi kommer att ge steg-för-steg-vägledning, tillsammans med ett kodexempel, för att hjälpa dig uppnå detta.

## Steg 1: Ladda en befintlig PDF-fil

Först måste vi ladda en befintlig PDF-fil. För den här handledningen kommer vi att använda filen "42824.pdf" som finns i katalogen "DIN DOKUMENTKATOLOG". Ersätt denna katalogsökväg med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Steg 2: Lägga till en innehållsförteckningssida

 Därefter måste vi lägga till en ny sida i början av dokumentet för att fungera som innehållsförteckningssida. Vi kan uppnå detta genom att använda`Insert()` metod för`Pages` samling av`Document` objekt.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Steg 3: Skapa ett TOC-objekt

 För att skapa ett TOC-objekt måste vi först skapa ett`TocInfo`objekt och ställ in dess egenskaper. I den här handledningen kommer vi att ställa in titeln på innehållsförteckningen till "Innehållsförteckning" och sidnummerprefixet till "P".

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Steg 4: Skapa TOC-poster

För att skapa TOC-poster måste vi gå igenom alla sidor i dokumentet, förutom innehållsförteckningssidan, och skapa ett rubrikobjekt för varje sida. Vi kan sedan lägga till rubrikobjektet på TOC-sidan och ange dess målsida.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Skapa rubrikobjekt
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Ange målsidan för rubrikobjektet
    heading2.DestinationPage = doc.Pages[i + 1];
    // Destinationssida
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Destinationskoordinat
    segment2.Text = "Page " + i.ToString();
    // Lägg till rubrik på sidan som innehåller innehållsförteckningen
    tocPage.Paragraphs.Add(heading2);
}
```

## Steg 5: Spara det uppdaterade dokumentet

 Slutligen måste vi spara det uppdaterade dokumentet till en ny fil. Vi kan uppnå detta genom att använda`Save()` metod för`Document` objekt.

```csharp
doc.Save(outFile);
```

### Exempel på källkod för att anpassa sidnummer samtidigt som TOC läggs till med Aspose.PDF för .NET

```csharp

            
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            string inFile = dataDir + "42824.pdf";
            string outFile = dataDir + "42824_out.pdf";
            // Ladda en befintlig PDF-fil
            Document doc = new Document(inFile);
            // Få tillgång till första sidan av PDF-filen
            Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
            // Skapa objekt för att representera TOC-information
            TocInfo tocInfo = new TocInfo();
            TextFragment title = new TextFragment("Table Of Contents");
            title.TextState.FontSize = 20;
            title.TextState.FontStyle = FontStyles.Bold;
            // Ställ in titeln för TOC
            tocInfo.Title = title;
            tocInfo.PageNumbersPrefix = "P";
            tocPage.TocInfo = tocInfo;
            for (int i = 1; i<doc.Pages.Count; i++)
            {
                // Skapa rubrikobjekt
                Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
                TextSegment segment2 = new TextSegment();
                heading2.TocPage = tocPage;
                heading2.Segments.Add(segment2);
                // Ange målsidan för rubrikobjektet
                heading2.DestinationPage = doc.Pages[i + 1];
                // Destinationssida
                heading2.Top = doc.Pages[i + 1].Rect.Height;
                // Destinationskoordinat
                segment2.Text = "Page " + i.ToString();
                // Lägg till rubrik på sidan som innehåller innehållsförteckningen
                tocPage.Paragraphs.Add(heading2);
            }

            //Spara det uppdaterade dokumentet
            doc.Save(outFile);
            
        
```

## Slutsats

I den här handledningen har vi gett steg-för-steg-vägledning om hur man anpassar sidnummer samtidigt som man lägger till en innehållsförteckning med Aspose.PDF för .NET. Vi har också tillhandahållit ett kodexempel som du kan använda som referens när du implementerar den här funktionen i din

