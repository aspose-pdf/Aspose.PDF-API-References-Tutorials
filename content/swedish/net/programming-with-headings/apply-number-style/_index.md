---
title: Använd nummerstil i PDF-fil
linktitle: Använd nummerstil i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du tillämpar en numreringsstil på rubriker i PDF-fil med Aspose.PDF för .NET. Steg för steg guide.
type: docs
weight: 10
url: /sv/net/programming-with-headings/apply-number-style/
---
I den här handledningen går vi igenom följande C#-källkod steg för steg för att tillämpa numreringsstil i PDF-fil med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

### Steg 1: Installation av dokumentkatalog

I den medföljande källkoden måste du ange katalogen där du vill spara den genererade PDF-filen. Ändra variabeln "dataDir" till önskad katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Steg 2: Skapa PDF-dokumentet

Vi skapar ett nytt PDF-dokument med specificerade mått och marginaler.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### Steg 3: Skapa en sida och flytande behållare

Vi lägger till en sida i dokumentet och skapar en flytande behållare för att organisera innehållet.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### Steg 4: Lägg till rubriker med numrering

Vi skapar rubriker med specificerade numrering och lägger till dem i den flytande behållaren.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### Steg 5: Spara PDF-dokumentet

Vi sparar det genererade PDF-dokumentet i den angivna katalogen.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Exempel på källkod för Apply Number Style med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Slutsats

I den här handledningen förklarade vi hur man tillämpar en numreringsstil på rubriker i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att skapa PDF-dokument med anpassade numrering för rubriker.

### Vanliga frågor för att tillämpa nummerstil i PDF-fil

#### F: Vad är numreringsstil i ett PDF-dokument?

S: Numreringsstil hänvisar till formatet i vilket rubriker eller avsnitt numreras i ett PDF-dokument. Det kan innehålla siffror, bokstäver eller andra tecken för att ge en hierarkisk struktur.

#### F: Varför skulle jag behöva tillämpa numreringsstil på rubriker i ett PDF-dokument?

S: Genom att använda numreringsstil på rubriker förbättras läsbarheten och organisationen av ditt PDF-dokument. Det hjälper läsarna att enkelt navigera och förstå innehållets hierarkiska struktur.

#### F: Vad är Aspose.PDF för .NET?

S: Aspose.PDF för .NET är ett bibliotek som låter utvecklare arbeta med PDF-filer programmatiskt i .NET-applikationer. Den tillhandahåller ett brett utbud av funktioner för att skapa, redigera, konvertera och manipulera PDF-dokument.

#### F: Hur importerar jag de nödvändiga biblioteken för mitt C#-projekt?

S: För att importera de nödvändiga biblioteken för ditt C#-projekt, inkludera följande importdirektiv:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Dessa direktiv ger dig tillgång till de klasser och metoder som behövs för att arbeta med PDF-dokument och tillämpa numreringsstilar.

#### F: Hur anger jag katalogen för att spara den genererade PDF-filen?

S: I den medföljande källkoden, ändra variabeln "dataDir" för att ange katalogen där du vill spara den genererade PDF-filen.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogsökvägen.

#### F: Hur skapar jag ett PDF-dokument med specificerade mått och marginaler?

S: För att skapa ett PDF-dokument med specificerade mått och marginaler, använd följande kod:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### F: Hur lägger jag till rubriker med numreringsstil till PDF-dokumentet?

S: För att lägga till rubriker med numreringsstil till PDF-dokumentet, använd de medföljande kodexemplen för att skapa rubriker och anpassa deras numreringsstilar. Justera egenskaper som text, numreringsstil, startnummer och automatisk sekvens efter behov.

#### F: Hur sparar jag det genererade PDF-dokumentet?

 S: För att spara det genererade PDF-dokumentet, använd`Save` metod för`pdfDoc` objekt:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### F: Hur kan jag bekräfta att numreringsstilen har tillämpats?

S: Öppna den genererade PDF-filen för att verifiera att den angivna numreringsstilen har tillämpats på rubrikerna.

#### F: Kan jag anpassa numreringsstilen ytterligare?

 S: Ja, du kan anpassa numreringsstilen ytterligare genom att justera egenskaperna för`Heading` objekt, som numreringsstilstyp, startnummer och autosekvens.

#### F: Kan jag använda olika numreringsstilar på olika delar av dokumentet?

S: Ja, du kan använda olika numreringsstilar på olika delar av dokumentet genom att skapa flera`Heading` objekt med olika stilar och sekvenser.