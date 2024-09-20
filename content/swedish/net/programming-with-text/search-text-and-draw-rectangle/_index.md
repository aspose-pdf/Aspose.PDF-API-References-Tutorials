---
title: Sök text och rita rektangel
linktitle: Sök text och rita rektangel
second_title: Aspose.PDF för .NET API Referens
description: Lär dig att söka text i PDF-filer och markera den med rektanglar med Aspose.PDF för .NET! Enkel steg-för-steg handledning för förbättrade färdigheter i PDF-manipulation.
type: docs
weight: 460
url: /sv/net/programming-with-text/search-text-and-draw-rectangle/
---
## Introduktion

Vill du förbättra dina färdigheter i PDF-manipulation? Vill du lära dig hur du söker efter specifik text i PDF-filer och markerar den med en rektangel? Du har landat på den perfekta guiden! Idag ska jag gå igenom hur du använder Aspose.PDF för .NET för att söka efter text i ett PDF-dokument och rita rektanglar runt det. Den här artikeln kommer att ge en steg-för-steg handledning utformad med tydlighet och användbarhet i åtanke, vilket säkerställer att du kan följa med och tillämpa dessa tekniker i dina projekt. 

## Förutsättningar

Innan vi dyker in i handledningen, låt oss förbereda vad du behöver för att säkerställa ett smidigt arbetsflöde:

1. Grundläggande förståelse för .NET: Du bör vara bekant med C#-programmering och .NET-ramverket för att kunna följa denna handledning på ett effektivt sätt.
   
2. Visual Studio installerad: Du behöver en integrerad utvecklingsmiljö (IDE) för att skriva och testa din kod. Visual Studio Community är ett bra alternativ, och det är gratis.
   
3. Aspose.PDF för .NET: Du måste ha Aspose.PDF-biblioteket installerat i ditt projekt. Du kan ladda ner den[här](https://releases.aspose.com/pdf/net/) eller överväga en[tillfällig licens](https://purchase.aspose.com/temporary-license/) för utökade funktioner.
   
4.  Exempel på PDF-dokument: För denna handledning behöver du ett exempel på PDF-fil med namnet`SearchAndGetTextFromAll.pdf` lagras i din projektkatalog. 

## Importera paket

För att komma igång måste du först importera de nödvändiga paketen till ditt .NET-projekt. Följ dessa steg:

### Öppna Visual Studio

Starta Visual Studio och skapa en ny konsolapplikation eller använd en befintlig där du vill implementera PDF-funktionerna.

### Lägg till Aspose.PDF till ditt projekt

1. Högerklicka på ditt projekt i Solution Explorer.
2. Välj "Hantera NuGet-paket."
3.  Leta efter`Aspose.PDF` och installera den senaste versionen.

Genom att göra detta lägger du grunden för alla fantastiska PDF-manipulationer du ska utföra.

## Importera namnområden

Överst i din programfil vill du importera de relevanta namnområdena från Aspose-biblioteket:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

Detta gör det lättare att komma åt klasser och metoder inom Aspose.PDF-biblioteket för dina uppgifter.


Nu när du har allt inställt, låt oss dela upp processen att söka efter text i en PDF och rita en rektangel runt den i hanterbara steg.

## Steg 1: Ställ in sökvägen för ditt dokument

 Ange först sökvägen till din PDF-fil. Se till att byta ut`YOUR DOCUMENT DIRECTORY` med den faktiska vägen där din`SearchAndGetTextFromAll.pdf` lagras.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet

 Skapa sedan en instans av`Document` klass för att ladda din PDF:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Denna kodrad öppnar din specificerade PDF-fil, så att du kan manipulera den ytterligare.

## Steg 3: Skapa en textabsorberare

 Nu behöver du ett sätt att söka efter text i det dokumentet. För detta använder vi`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Det reguljära uttrycket`@"[\S]+"` är utformad för att matcha alla icke-blankstegssträngar i PDF-filen. 

## Steg 4: Konfigurera textsökningsalternativ

Därefter bör du ställa in alternativen för textsökning:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Här, den`true` parametern betyder att sökningen är skiftlägeskänslig. Du kan ställa in den på`false` om du vill ha en skiftlägesokänslig sökning.

## Steg 5: Acceptera Text Absorber i dokumentet

 Med din`TextFragmentAbsorber` och sökalternativ redo, är det dags att absorbera text från dokumentet:

```csharp
document.Pages.Accept(textAbsorber);
```

Den här metoden undersöker varje sida i din PDF för att hitta textfragment som matchar det angivna mönstret.

## Steg 6: Skapa en PdfContentEditor

 För att rita former på dokumentet behöver du`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Med den här redigeraren kan du enkelt manipulera och redigera PDF-innehållet.

## Steg 7: Gå igenom hittade textfragment

Nu vill du gå igenom de hittade textfragmenten för att rita rektanglar runt dem:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Denna loop itererar över varje textfragment och deras segment och anropar a`DrawBox` metod för rektangelritning.

## Steg 8: Definiera DrawBox-metoden

 Du måste definiera`DrawBox` metod, som kommer att hantera rektangelritningslogiken. Här är en enkel implementering:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Beräkna rektangeldimensionerna baserat på textsegmentet
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Rita en rektangel med hjälp av de beräknade värdena
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Den här metoden bestämmer rektangelns position och storlek baserat på segmentets avgränsande rektangel och använder editorn för att rita den.

## Steg 9: Spara det ändrade dokumentet

Efter att ha ritat rektanglarna runt den hittade texten kan du spara det ändrade dokumentet:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Se till att din nya fil sparas med ett distinkt namn för att undvika att ditt originaldokument skrivs över.

## Steg 10: Bekräftelsemeddelande

Skriv slutligen ut ett bekräftelsemeddelande till konsolen för att låta dig veta att operationen lyckades:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

Och där har du det! Du har framgångsrikt skapat ett skript för att söka efter text i en PDF och markera den med rektanglar.

## Slutsats

Grattis! Du har precis låst upp en kraftfull färdighet som avsevärt kan förbättra dina PDF-manipuleringsförmåga med Aspose.PDF för .NET. Med bara några enkla steg kan du söka efter vilken text som helst i ditt dokument och markera den visuellt, vilket gör dina PDF-dokument mer interaktiva och hanterbara. Tveka inte att experimentera med olika regexmönster och färgalternativ för att verkligen göra detta verktyg till ditt eget!

## FAQ's

### Vad är Aspose.PDF för .NET?
Aspose.PDF för .NET är ett bibliotek som ger ett omfattande sätt att skapa, manipulera och konvertera PDF-dokument programmatiskt.

### Kan jag använda Aspose.PDF gratis?
Ja, Aspose erbjuder en gratis provperiod som du kan använda för att testa bibliotekets funktioner. Kolla in det[här](https://releases.aspose.com/).

### Vilket programmeringsspråk behöver jag använda med Aspose.PDF för .NET?
Aspose.PDF för .NET är designad för att användas med C# och andra .NET-språk.

### Hur får jag hjälp med Aspose.PDF?
 Du kan besöka Asposes supportforum för att få hjälp angående alla problem eller frågor du kan ha. Hitta support[här](https://forum.aspose.com/c/pdf/10).

### Var laddar jag ner Aspose.PDF för .NET?
 Du kan ladda ner biblioteket från Asposes webbplats,[här](https://releases.aspose.com/pdf/net/).