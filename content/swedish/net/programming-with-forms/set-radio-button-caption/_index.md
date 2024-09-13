---
title: Ställ in radioknappstext
linktitle: Ställ in radioknappstext
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in alternativknappstexter i PDF-filer med Aspose.PDF för .NET. Den här steg-för-steg-guiden leder dig genom att ladda, ändra och spara dina PDF-formulär.
type: docs
weight: 280
url: /sv/net/programming-with-forms/set-radio-button-caption/
---
## Introduktion

Om du dyker in i PDF-manipulation med Aspose.PDF för .NET, har du en njutning! Idag fokuserar vi på en praktisk funktion: att ställa in alternativknappstexter i dina PDF-formulär. Radioknappar är viktiga för användarformulär där du behöver välja bland en uppsättning alternativ. Föreställ dig dem som flervalsfrågor där endast ett svar är tillåtet. Den här handledningen leder dig genom processen att uppdatera alternativknappstexterna i en PDF-form, så att dina dokument är både interaktiva och användarvänliga. 

## Förutsättningar

Innan du dyker in i koden finns det några saker du måste se till att du har:

1. Aspose.PDF för .NET: Se till att du har Aspose.PDF-biblioteket installerat. Det här biblioteket hjälper dig att manipulera PDF-filer programmatiskt.
2. Utvecklingsmiljö: Du bör ha en .NET-utvecklingsmiljö inställd, till exempel Visual Studio.
3. Exempel på PDF-formulär: För den här handledningen behöver du ett exempel på PDF-formulär med alternativknappar. Du kan använda vilket befintligt PDF-formulär som helst eller skapa ett nytt med alternativknappar.
4. Grundläggande kunskaper om C#: Den här guiden förutsätter att du har en grundläggande förståelse för C# och .NET programmeringskoncept.

 Om du ännu inte har installerat Aspose.PDF för .NET eller om du behöver en tillfällig licens kan du[ladda ner den här](https://releases.aspose.com/pdf/net/) eller[få en tillfällig licens](https://purchase.aspose.com/temporary-license/).

## Importera paket

För att komma igång måste du importera nödvändiga paket i ditt C#-projekt. Så här inkluderar du Aspose.PDF-biblioteket:

```csharp
using System;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
using Aspose.Pdf.Text;
```

Se till att du har lagt till dessa paket till ditt projekt via NuGet eller din föredragna metod.

## Steg 1: Ladda PDF-formuläret

 Först måste du ladda PDF-formuläret som innehåller alternativknapparna. De`Aspose.Pdf.Facades.Form`klass används för detta ändamål. Så här gör du:

```csharp
// Definiera sökvägen till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda käll-PDF-formuläret
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
```

I detta kodavsnitt:
- `dataDir` anger sökvägen där din PDF-fil finns.
- `Form` klass används för att interagera med formulärfälten i PDF:en.
- `Document` klass ger tillgång till PDF-dokumentets sidor.

## Steg 2: Iterera genom radioknappsfält

Därefter måste du iterera genom fälten i ditt formulär för att identifiera och manipulera alternativknappsfälten:

```csharp
foreach (var item in form1.FieldNames)
{
    Console.WriteLine(item.ToString());
    Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
```

I denna loop:
- `FieldNames` ger en lista över alla fältnamn i PDF-filen.
- `GetButtonOptionValues(item)` hämtar de tillgängliga alternativen för varje alternativknapp.

## Steg 3: Ändra alternativ för alternativknapp

 När du har identifierat alternativknappsfälten kan du ändra deras alternativ. För detta måste du kasta fältet till`RadioButtonField` och uppdatera dess alternativ:

```csharp
    if (item.Contains("radio1"))
    {
        Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
        Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
        fieldoption.OptionName = "Yes";
        fieldoption.PartialName = "Yesname";
```

Här:
- Vi kontrollerar om fältnamnet innehåller "radio1" för att identifiera det specifika alternativknappsfältet vi vill ändra.
- `RadioButtonField`casts från formulärfälten för att göra specifika ändringar.

## Steg 4: Ställ in bildtexten för radioknappen

 För att ställa in eller uppdatera bildtexten för alternativknappen måste du skapa en`TextFragment` och använda`TextBuilder` för att placera den på önskad plats:

```csharp
        var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
        updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
        updatedFragment.TextState.FontSize = 10;
        updatedFragment.TextState.LineSpacing = 6.32f;

        // Skapa TextParagraph-objekt
        TextParagraph par = new TextParagraph();
        // Ställ in styckeposition
        par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
        // Ange radbrytningsläge
        par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
        // Lägg till nytt textfragment till stycket
        par.AppendLine(updatedFragment);
        // Lägg till TextParagraph med TextBuilder
        TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
        textBuilder.AppendParagraph(par);
```

I denna del:
- `TextFragment` används för att definiera texten och dess utseende.
- `TextParagraph` hjälper till att placera och formatera texten.
- `TextBuilder` lägger till texten på den angivna sidan i PDF-filen.

## Steg 5: Spara den uppdaterade PDF-filen

Slutligen, spara den uppdaterade PDF-filen till en ny fil:

```csharp
        field0.DeleteOption("item1");
    }
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Detta kommer att säkerställa att:
- Ändringarna tillämpas på PDF-filen.
- Det ursprungliga alternativknappsalternativet tas bort som specificerat.

## Slutsats

Ändring av alternativknappstexter i en PDF-form med Aspose.PDF för .NET kan avsevärt förbättra interaktiviteten och användbarheten av dina dokument. Med stegen som beskrivs i denna handledning kan du enkelt ladda en PDF, uppdatera alternativ för alternativknappar och spara dina ändringar. Detta tillvägagångssätt är praktiskt för formulärhantering och säkerställer att dina PDF-filer uppfyller dina användares exakta behov. Dyk in i Aspose.PDF och utforska dess möjligheter för andra PDF-manipulationer!

## FAQ's

### Kan jag uppdatera flera alternativknappsfält samtidigt?
Ja, du kan iterera genom alla alternativknappsfält och tillämpa ändringar efter behov.

### Behöver jag en licens för att använda Aspose.PDF?
 Du kan börja med en gratis provperiod, men en licens krävs för utökad användning.[Skaffa en licens här](https://purchase.aspose.com/buy).

### Hur kan jag testa ändringarna innan jag sparar PDF-filen?
Du kan förhandsgranska PDF-filen i din utvecklingsmiljö eller använda en PDF-visare för att kontrollera ändringarna.

### Är Aspose.PDF kompatibel med alla versioner av .NET?
Aspose.PDF stöder olika versioner av .NET. Se till att du kontrollerar kompatibiliteten med din specifika .NET-version.

### Kan jag manipulera andra formulärfält på liknande sätt?
Ja, liknande tekniker kan tillämpas på andra typer av formulärfält i PDF-dokument.