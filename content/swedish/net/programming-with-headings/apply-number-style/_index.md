---
title: Använd nummerstil i PDF-fil
linktitle: Använd nummerstil i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du tillämpar olika talstilar (romerska siffror, alfabetiska) på rubriker i en PDF med Aspose.PDF för .NET med denna steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/programming-with-headings/apply-number-style/
---
## Introduktion

Har du någonsin sett att du behöver lägga till vackert numrerade listor till dina PDF-dokument? Oavsett om du formaterar juridiska dokument, rapporter eller presentationer, är korrekta numreringsstilar viktiga för att organisera information. Med Aspose.PDF för .NET kan du använda olika numreringsstilar på din PDF-fils rubriker och skapa välstrukturerade och professionella dokument. 

## Förutsättningar

Innan vi går in i kodning, låt oss gå igenom vad du behöver:

1. Aspose.PDF för .NET: Ladda ner den senaste versionen av Aspose.PDF från[här](https://releases.aspose.com/pdf/net/).
2. Utvecklingsmiljö: Se till att du har Visual Studio eller någon annan .NET-kompatibel IDE.
3. .NET Framework: Se till att du har .NET Framework 4.0 eller senare installerat.
4.  Licens: Du kan använda en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/) eller utforska[gratis provperiod](https://releases.aspose.com/) alternativ.

## Importera paket

För att komma igång, se till att du har följande namnrymder importerade i ditt projekt:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Steg 1: Konfigurera dokumentet

Låt oss börja med att skapa ett nytt PDF-dokument och konfigurera dess sidinställningar. Vi kommer att ställa in sidstorlek och marginaler för att styra layouten på vårt innehåll.

Förklaring: I det här steget ställer vi in den grundläggande strukturen för PDF:en, som inkluderar att definiera sidstorlek, höjd och marginaler för konsekvent formatering.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Ställ in sidmått och marginaler
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

Genom att göra detta kommer ditt dokument att ha en standard sidstorlek, motsvarande en 8,5 x 11-tums sida, och en marginal på 72 punkter (eller 1 tum) på alla sidor.

## Steg 2: Lägga till en sida till PDF-filen

Därefter lägger vi till en ny sida i PDF-dokumentet där vi senare kommer att tillämpa numreringsstilarna.

Förklaring: Varje PDF kräver sidor! Det här steget lägger till en tom sida i PDF-filen och ställer in dess marginaler så att de matchar inställningarna på dokumentnivå.

```csharp
// Lägg till en ny sida i PDF-dokumentet
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## Steg 3: Skapa en flytande låda

En FloatingBox låter dig placera innehåll (som text eller rubriker) i en ruta som beter sig oberoende av sidans flöde. Detta är användbart när du vill ha fullständig kontroll över layouten för ditt innehåll.

Förklaring: Här sätter vi upp en FloatingBox för att innehålla rubrikerna som kommer att ha nummerstilar tillämpade.

```csharp
// Skapa en FloatingBox för strukturerat innehåll
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## Steg 4: Lägg till den första rubriken med romerska siffror

Nu kommer den spännande delen! Låt oss lägga till den första rubriken med gemener romerska siffror.

Förklaring: Vi använder stilen NumberingStyle.NumeralsRomanGemena bokstäver på rubriken, som visar numrering i romerska siffror (i, ii, iii, etc.).

```csharp
// Skapa den första rubriken med romerska siffror
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## Steg 5: Lägg till en andra rubrik för romerska siffror

För demonstrationsändamål, låt oss lägga till en andra romersk siffra, men den här gången börjar vi från 13.

Förklaring: Egenskapen StartNumber låter dig börja numrera från ett anpassat nummer – i det här fallet börjar vi från 13.

```csharp
// Skapa en andra rubrik som börjar med romersk siffra 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## Steg 6: Lägg till en rubrik med alfabetisk numrering

För variation, låt oss lägga till en tredje rubrik, men den här gången kommer vi att använda alfabetisk numrering med gemener (a, b, c, etc.).

Förklaring: Genom att ändra numreringsstilen till bokstäver med små bokstäver kan vi använda alfabetisk numrering på våra rubriker.

```csharp
// Skapa en rubrik med alfabetisk numrering
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## Steg 7: Spara PDF-filen

Slutligen, efter att ha tillämpat alla rubriker och nummerstilar, låt oss spara PDF-filen i önskad katalog.

Förklaring: Detta steg sparar PDF-filen som innehåller alla formaterade rubriker med tillämpade numreringsstilar.

```csharp
// Spara PDF-dokumentet
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## Slutsats

Och där har du det! Du har framgångsrikt tillämpat numreringsstilar – romerska siffror och alfabetiska – på rubriker i en PDF-fil med Aspose.PDF för .NET. Flexibiliteten från Aspose.PDF för att kontrollera sidlayout, numreringsstilar och innehållspositionering ger dig en kraftfull verktygsuppsättning för att skapa välorganiserade, professionella PDF-dokument.

## FAQ's

### Kan jag använda olika nummerstilar på samma PDF-dokument?  
Ja, Aspose.PDF för .NET låter dig blanda olika numreringsstilar som romerska siffror, arabiska siffror och alfabetisk numrering inom samma dokument.

### Hur kan jag anpassa startnumret för rubriker?  
 Du kan ställa in startnumret för vilken rubrik som helst genom att använda`StartNumber` egendom.

### Finns det något sätt att återställa numreringssekvensen?  
Ja, du kan återställa numreringen genom att justera`StartNumber` egendom för varje rubrik.

### Kan jag använda fet eller kursiv stil på rubriker utöver numrering?  
 Absolut! Du kan anpassa rubrikstilar genom att ändra egenskaper som typsnitt, storlek, fetstil och kursiv med`TextState` objekt.

### Hur får jag en tillfällig licens för Aspose.PDF?  
 Du kan få en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/) för att testa Aspose.PDF utan begränsningar.