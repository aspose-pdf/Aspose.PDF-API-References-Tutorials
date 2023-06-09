---
title: Skapa lokal hyperlänk
linktitle: Skapa lokal hyperlänk
second_title: Aspose.PDF för .NET API Referens
description: Skapa enkelt lokala hyperlänkar i en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/programming-with-links-and-actions/create-local-hyperlink/
---

Genom att skapa lokala hyperlänkar i en PDF-fil kan du skapa klickbara länkar som tar användare till andra sidor i samma PDF-dokument. Med Aspose.PDF för .NET kan du enkelt skapa sådana länkar genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen där du vill spara den resulterande PDF-filen. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Skapa en instans av Document

 Vi kommer att skapa en instans av`Document` klass för att representera vårt PDF-dokument. Här är motsvarande kod:

```csharp
Document doc = new Document();
```

## Steg 4: Lägg till sida och text med hyperlänkar

det här steget kommer vi att lägga till en sida i vårt PDF-dokument och lägga till lite text som innehåller lokala hyperlänkar. Vi kommer att definiera målsidorna för varje länk. Här är motsvarande kod:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Steg 5: Spara det uppdaterade dokumentet

Låt oss nu spara den uppdaterade PDF-filen med hjälp av`Save` metod för`doc` objekt. Här är motsvarande kod:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Exempel på källkod för Skapa lokal hyperlänk med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Skapa dokumentinstans
Document doc = new Document();
// Lägg till sida till sidor samling av PDF-fil
Page page = doc.Pages.Add();
// Skapa Text Fragment-instans
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Skapa lokal hyperlänksinstans
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Ställ in målsida för länkinstans
link.TargetPageNumber = 7;
// Ställ in TextFragment hyperlänk
text.Hyperlink = link;
// Lägg till text i styckesamlingen på sidan
page.Paragraphs.Add(text);
// Skapa ny TextFragment-instans
text = new TextFragment("link page number test to page 1");
// TextFragment bör läggas till över ny sida
text.IsInNewPage = true;
// Skapa ytterligare en lokal hyperlänksinstans
link = new LocalHyperlink();
// Ställ in målsida för den andra hyperlänken
link.TargetPageNumber = 1;
// Ställ in länk för andra TextFragment
text.Hyperlink = link;
// Lägg till text till styckesamling av sidobjekt
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Spara uppdaterat dokument
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Slutsats

Grattis! Nu har du en steg-för-steg-guide för att skapa lokala hyperlänkar i en PDF med Aspose.PDF för .NET. Du kan använda den här koden för att skapa klickbara länkar som tar användare till andra sidor i samma dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade hyperlänkfunktioner.