---
title: Sök text och rita rektangel
linktitle: Sök text och rita rektangel
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du söker efter text i en PDF, ritar rektanglar runt den hittade texten och sparar det modifierade dokumentet med Aspose.PDF för .NET.
type: docs
weight: 460
url: /sv/net/programming-with-text/search-text-and-draw-rectangle/
---
Denna handledning förklarar hur du använder Aspose.PDF för .NET för att söka efter specifik text i ett PDF-dokument, rita en rektangel runt den hittade texten och spara det ändrade dokumentet. Den medföljande C#-källkoden demonstrerar processen steg för steg.

## Förutsättningar

Innan du fortsätter med handledningen, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller använda NuGet för att installera det i ditt projekt.

## Steg 1: Konfigurera projektet

Börja med att skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnutrymmen

Lägg till följande med hjälp av direktiv i början av din C#-fil för att importera de nödvändiga namnrymden:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Steg 3: Ställ in sökvägen till dokumentkatalogen

 Ställ in sökvägen till din dokumentkatalog med hjälp av`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Ladda PDF-dokumentet

 Ladda PDF-dokumentet med hjälp av`Document` klass:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Ersätta`"SearchAndGetTextFromAll.pdf"` med det faktiska namnet på din PDF-fil.

## Steg 5: Skapa en TextFragmentAbsorber

 Skapa en`TextFragmentAbsorber` objekt för att hitta alla instanser av den inmatade sökfrasen:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Ersätta`@"[\S]+"` med ditt önskade reguljära uttrycksmönster.

## Steg 6: Aktivera sökning i reguljära uttryck

 Aktivera sökning efter reguljära uttryck genom att ställa in`TextSearchOptions` absorbatorns egenskaper:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Steg 7: Sök på alla sidor

Acceptera absorbenten för alla sidor i dokumentet:

```csharp
document.Pages.Accept(textAbsorber);
```

## Steg 8: Rita en rektangel runt den hittade texten

 Skapa en`PdfContentEditor` objekt och loop genom de hämtade textfragmenten, rita en rektangel runt varje textsegment:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Steg 9: Spara det ändrade dokumentet

Spara det ändrade dokumentet:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Se till att byta ut`"SearchTextAndDrawRectangle_out.pdf"` med önskat utdatafilnamn.

### Exempel på källkod för Sök text och rita rektangel med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//Skapa TextAbsorber-objekt för att hitta alla fraser som matchar det reguljära uttrycket
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du söker efter specifik text i ett PDF-dokument, ritar en rektangel runt den hittade texten och sparar det modifierade dokumentet med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att ställa in projektet till att utföra de nödvändiga åtgärderna. Du kan nu infoga den här koden i dina egna C#-projekt för att manipulera text och rita rektanglar i PDF-filer.

### FAQ's

#### F: Vad är syftet med handledningen "Sök text och rita rektangel"?

S: Handledningen "Sök text och rita rektangel" syftar till att vägleda användare genom processen att använda Aspose.PDF-biblioteket för .NET för att söka efter specifik text i ett PDF-dokument, rita rektanglar runt de hittade textsegmenten och spara de modifierade dokumentera. Handledningen innehåller detaljerade instruktioner och C#-kodexempel för att illustrera varje steg i processen.

#### F: Hur hjälper den här handledningen till att rita rektanglar runt specifik text i ett PDF-dokument?

S: Den här handledningen ger en omfattande guide om hur du hittar och ritar rektanglar runt specifika textsegment i ett PDF-dokument. Den demonstrerar processen att ställa in ett projekt, ladda ett PDF-dokument, möjliggöra sökning i reguljära uttryck, rita rektanglar runt hittade textsegment och spara den modifierade PDF-filen.

#### F: Vilka förutsättningar krävs för att följa denna handledning?

S: Innan du startar handledningen bör du ha en grundläggande förståelse för programmeringsspråket C#. Dessutom måste du ha Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller installera det i ditt projekt med NuGet.

#### F: Hur ställer jag in mitt projekt för att följa denna handledning?

S: Börja med att skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE). Lägg sedan till en referens till Aspose.PDF för .NET-biblioteket i ditt projekt. Detta gör att du kan använda bibliotekets funktionalitet för att manipulera PDF-dokument.

#### F: Kan jag rita rektanglar runt specifik text med den här handledningen?

S: Ja, handledningen fokuserar på att rita rektanglar runt specifika textsegment i ett PDF-dokument. Den visar hur man lokaliserar den önskade texten med hjälp av reguljära uttryck, skapar rektanglar runt de identifierade textsegmenten och sparar den modifierade PDF-filen.

#### F: Hur kan jag specificera texten jag vill söka efter och rita rektanglar runt?

 S: För att ange texten du vill söka efter och rita rektanglar runt, skapa en`TextFragmentAbsorber` objekt och ställ in dess mönster med hjälp av`Text` parameter. Byt ut standardmönstret`@"[\S]+"` i handledningens kod med ditt önskade reguljära uttrycksmönster.

#### F: Hur aktiverar jag sökning i reguljära uttryck efter text?

 S: Reguljära uttryckssökning aktiveras genom att skapa en`TextSearchOptions` objekt och ställer in dess värde till`true` . Tilldela detta objekt till`TextSearchOptions` egendom av`TextFragmentAbsorber` exempel. Detta säkerställer att det reguljära uttrycksmönstret används under textsökning.

#### F: Hur ritar jag rektanglar runt den hittade texten?

 S: Efter att ha identifierat textsegmenten med hjälp av`TextFragmentAbsorber` , ger handledningen en loop för att iterera genom dessa segment. För varje textsegment visar handledningen hur man skapar en rektangel runt det med hjälp av`DrawBox` metod och ange rektangelns utseende.

#### F: Vilka är stegen för att spara den modifierade PDF-filen med ritade rektanglar?

S: Efter att ha ritat rektanglar runt de önskade textsegmenten, använd`Document` klass`Save` metod för att spara det ändrade dokumentet. Handledningens exempelkod visar hur du sparar den redigerade PDF-filen och visar ett framgångsmeddelande.

#### F: Kan jag anpassa utseendet på de ritade rektanglarna?

 S: Ja, du kan anpassa utseendet på de ritade rektanglarna. I handledningens exempelkod,`DrawBox` Metoden används för att skapa rektanglar. Du kan ändra egenskaper som färg, stil och tjocklek för att anpassa utseendet på de ritade rektanglarna.