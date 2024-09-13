---
title: Ställ in bildtextegenskap i PDF-fil
linktitle: Ställ in bildtextegenskap i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in bildtext-egenskapen i en PDF-fil med Aspose.PDF för .NET i denna detaljerade, steg-för-steg handledning.
type: docs
weight: 130
url: /sv/net/annotations/setcalloutproperty/
---
## Introduktion

Att skapa professionella och visuellt tilltalande PDF-dokument kräver ofta tillägg av kommentarer som uppmärksammar specifikt innehåll. En sådan kommentar är bildtexten, som är som de pratbubblor du ser i serier. De hjälper till att förtydliga eller betona text i din PDF. Aspose.PDF för .NET gör det otroligt enkelt att lägga till sådana kommentarer till dina dokument, och i den här handledningen går vi igenom hur du ställer in bildtextegenskapen i en PDF-fil med detta kraftfulla bibliotek. Oavsett om du är en erfaren utvecklare eller precis har börjat, i slutet av den här guiden har du en tydlig förståelse för hur du arbetar med länktexter i PDF-filer.

## Förutsättningar

Innan vi dyker in i koden, låt oss täcka det väsentliga du behöver för att komma igång.

1.  Aspose.PDF för .NET: Se till att du har Aspose.PDF för .NET-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/pdf/net/).
2. IDE: En utvecklingsmiljö som Visual Studio.
3. .NET Framework: Se till att du har .NET installerat på din dator.
4. Tillfällig licens: Om du vill prova alla funktioner i Aspose.PDF utan begränsningar, skaffa en[tillfällig licens](https://purchase.aspose.com/temporary-license/).

## Importera paket

Innan du börjar skriva koden måste du importera nödvändiga paket som gör att du kan arbeta med PDF-filer och anteckningar.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Dessa importer ger dig alla nödvändiga klasser och metoder för att manipulera PDF-dokument och skapa anteckningar som bildtexten.

## Steg 1: Initiera PDF-dokumentet

Det första steget i vår resa är att initiera ett nytt PDF-dokument där vi lägger till vår förklaringsanteckning. Se det här som att sätta upp en tom duk där du kan börja lägga till element.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initiera ett nytt PDF-dokument
Document doc = new Document();
```
 Här skapar vi en ny`Document` objekt som kommer att fungera som vår PDF-fil. De`dataDir` variabeln är inställd på katalogen där du vill spara din PDF-fil efter att vi är klara.

## Steg 2: Lägg till en ny sida i dokumentet

Ett PDF-dokument kan ha flera sidor, och i det här steget lägger vi till en ny sida i vårt dokument. Den här sidan kommer att vara där vår informationskommentar kommer att placeras.

```csharp
//Lägg till en ny sida i dokumentet
Page page = doc.Pages.Add();
```
 De`Pages.Add()`metod används för att lägga till en ny sida till`doc` objekt. Den nya sidan lagras i`page` variabel, som vi kommer att använda senare när vi lägger till anteckningen.

## Steg 3: Definiera standardutseendet

Annoteringar, som bildtexten, har ett visuellt utseende som du kan anpassa. I det här steget kommer vi att definiera hur texten i länktexten ska se ut.

```csharp
// Definiera standardutseendet för anteckningen
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Vi skapar en`DefaultAppearance` objekt som definierar textens färg och teckenstorlek. Här kommer texten att vara röd och teckenstorleken är inställd på 10. Detta utseende kommer att tillämpas på bildtextanteckningen.

## Steg 4: Skapa fritextkommentaren

Nu är det dags att skapa själva anteckningen. Fritextkommentaren är det som gör att vi kan lägga till en bildtext med specifik text och stil.

```csharp
// Skapa en FreeTextAnnotation med en förklaring
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Vi skapar en`FreeTextAnnotation` objekt med specifika koordinater som definierar dess position på sidan. De`Intent` är inställd på`FreeTextCallout` , vilket indikerar att detta är en förklaringskommentar. De`EndingStyle` är inställd på`OpenArrow`vilket betyder att textraden slutar med en öppen pil.

## Steg 5: Definiera bildtextlinjepunkterna

En förklaringskommentar har en linje som pekar på intresseområdet. Här kommer vi att definiera punkterna som utgör denna linje.

```csharp
// Definiera punkterna för textraden
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 De`Callout` egendom är en mängd`Point` objekt som vart och ett representerar en koordinat på sidan. Dessa punkter definierar sökvägen för textraden, vilket ger den det klassiska utseendet som en pratbubbla.

## Steg 6: Lägg till anteckningen på sidan

Efter att ha skapat och konfigurerat vår anteckning är nästa steg att lägga till den på sidan.

```csharp
// Lägg till anteckningen på sidan
page.Annotations.Add(fta);
```
 De`Annotations.Add()` metod används för att placera anteckningen på sidan vi skapade tidigare. Detta steg "ritar" effektivt bildtexten på PDF-sidan.

## Steg 7: Ställ in Rich Text Content

Förklaringskommentarer kan innehålla rik text, vilket möjliggör formaterat innehåll i bubblan. Låt oss lägga till lite exempeltext.

```csharp
// Ställ in rik text för anteckningen
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"färg:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Detta är ett exempel</span></p></body>";
```
 De`RichText` egenskapen ställs in med HTML-innehåll. Detta möjliggör detaljerad formatering i bildtexten, som att ange teckenstorlek, färg och stil.

## Steg 8: Spara PDF-dokumentet

Slutligen, efter att ha ställt in allt, måste vi spara dokumentet. Det här steget slutför skapandet av PDF-filen med förklaringskommentaren.

```csharp
// Spara dokumentet
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 De`Save()` metod sparar dokumentet i den angivna katalogen med filnamnet "SetCalloutProperty.pdf". Detta steg avslutar vår PDF-skapandeprocess.

## Slutsats

Och där har du det! Du har precis skapat ett PDF-dokument med en förklaringsanteckning med Aspose.PDF för .NET. Den här anteckningen kan vara otroligt användbar för att markera eller förklara specifika delar av ditt dokument. Aspose.PDF erbjuder ett kraftfullt API som gör PDF-manipulation enkel och flexibel. Oavsett om du lägger till kommentarer, konverterar dokument eller hanterar komplexa PDF-uppgifter, har Aspose.PDF dig täckt.

## FAQ's

### Kan jag anpassa utseendet på länktexten ytterligare?

Absolut! Du kan anpassa olika aspekter som linjefärg, tjocklek och textens teckensnittsfamilj och stil.

### Är det möjligt att lägga till flera länktexter på en enda sida?

Ja, du kan lägga till så många länktexter som behövs genom att upprepa stegen för varje anteckning.

### Hur ändrar jag positionen för bildtexten?

 Ändra helt enkelt koordinaterna i`Rectangle` och`Callout` egenskaper för att flytta annoteringen.

### Kan jag lägga till andra typer av kommentarer med Aspose.PDF?

Ja, Aspose.PDF stöder olika anteckningstyper, inklusive höjdpunkter, stämplar och filbilagor.

### Är rich text-innehållet begränsat till HTML?

 De`RichText` egenskapen stöder en delmängd av HTML, vilket gör att du kan inkludera formaterad text och grundläggande formatering.