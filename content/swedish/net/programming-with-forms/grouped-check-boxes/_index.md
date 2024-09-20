---
title: Grupperade kryssrutor i PDF-dokument
linktitle: Grupperade kryssrutor i PDF-dokument
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du skapar grupperade kryssrutor (radioknappar) i ett PDF-dokument med Aspose.PDF för .NET med denna steg-för-steg handledning.
type: docs
weight: 170
url: /sv/net/programming-with-forms/grouped-check-boxes/
---
## Introduktion

Att skapa interaktiva PDF-filer är inte så svårt som det kanske låter, särskilt när du har kraftfulla verktyg som Aspose.PDF för .NET till ditt förfogande. Ett av de interaktiva elementen du kan behöva lägga till i dina PDF-dokument är grupperade kryssrutor, eller mer specifikt alternativknappar som låter användare välja ett alternativ från en uppsättning. Denna handledning går igenom processen att lägga till grupperade kryssrutor (radioknappar) till ett PDF-dokument med Aspose.PDF för .NET. Oavsett om du är nybörjare eller erfaren utvecklare kommer du att tycka att den här guiden är engagerande, detaljerad och lätt att följa.

## Förutsättningar

Innan vi dyker in i steg-för-steg-guiden, låt oss täcka några viktiga förutsättningar:

1.  Aspose.PDF för .NET: Se till att du har Aspose.PDF-biblioteket installerat. Om inte, kan du[ladda ner den här](https://releases.aspose.com/pdf/net/).
2. IDE: Du bör ha en utvecklingsmiljö inställd, till exempel Visual Studio.
3. .NET Framework: Projektet bör inriktas på en version av .NET Framework som är kompatibel med Aspose.PDF.
4. Grundläggande C#-kunskaper: Förtrogenhet med C#- och PDF-manipulation krävs för att följa med smidigt.
5.  Licens: Aspose.PDF kräver en licens för full funktionalitet. Du kan[skaffa en tillfällig licens](https://purchase.aspose.com/temporary-license/) om det behövs.

## Importera paket

Innan du börjar, se till att du har importerat de nödvändiga namnrymden till ditt projekt:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

Dessa paket ger dig tillgång till alla klasser och metoder som krävs för att manipulera PDF-dokument, inklusive att skapa alternativknappar och definiera deras egenskaper.

I det här avsnittet delar vi upp processen för att skapa grupperade kryssrutor (radioknappar) i tydliga steg som är lätta att följa.

## Steg 1: Skapa ett nytt PDF-dokument

 Det första steget är att skapa en instans av`Document` objekt, som kommer att representera din PDF-fil. Lägg sedan till en tom sida i ditt dokument där du kommer att placera dina grupperade kryssrutor.

```csharp
// Instantiera dokumentobjekt
Document pdfDocument = new Document();

// Lägg till en sida i PDF-filen
Page page = pdfDocument.Pages.Add();
```

Detta lägger grunden för att lägga till alla element, såsom alternativknappar, till PDF-filen.

## Steg 2: Initiera radioknappfält

Därefter måste vi skapa en`RadioButtonField` objekt, som kommer att hålla de grupperade kryssrutorna (radioknappar). Detta fält läggs till på den specifika sida där kryssrutorna kommer att visas.

```csharp
// Instantiera RadioButtonField-objektet och tilldela det till första sidan
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

Se detta som behållaren som kommer att gruppera de individuella alternativen för alternativknappar.

## Steg 3: Lägg till alternativ för alternativknappar

 Låt oss nu lägga till de individuella alternativen för alternativknappar i fältet. I det här exemplet lägger vi till två alternativknappar och anger deras positioner med hjälp av`Rectangle` objekt.

```csharp
// Lägg till första alternativknappen och ange dess position med hjälp av rektangel
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Ställ in alternativnamn för identifiering
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 Här, den`Rectangle` objekt definierar koordinaterna och storleken för varje alternativknapp på sidan.

## Steg 4: Anpassa stilen på radioknappar

 Du kan anpassa utseendet på alternativknapparna genom att ställa in deras`Style` egendom. Till exempel kanske du vill ha kvadratiska kryssrutor eller korsformade.

```csharp
// Ställ in stilen på radioknapparna
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

Detta låter dig kontrollera utseendet och känslan av kryssrutorna, vilket gör dem mer användarvänliga och visuellt tilltalande.

## Steg 5: Konfigurera kantegenskaper

Gränser spelar en viktig roll för att göra kryssrutorna lätt identifierbara. Här lägger vi till fasta ramar runt varje alternativknapp och definierar deras bredd och färg.

```csharp
// Konfigurera gränsen för den första alternativknappen
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// Konfigurera gränsen för den andra alternativknappen
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

Detta steg säkerställer att varje alternativknapp har en väldefinierad ram, vilket förbättrar dokumentets läsbarhet.

## Steg 6: Lägg till alternativ för alternativknappar i formuläret

Nu lägger vi till alternativknapparna i dokumentets formulär. Detta är det sista steget i att gruppera kryssrutorna under ett enda fält.

```csharp
// Lägg till alternativknappsfält till dokumentets formulärobjekt
pdfDocument.Form.Add(radio);
```

Formobjektet fungerar som en behållare för alla interaktiva element, inklusive våra grupperade kryssrutor.

## Steg 7: Spara PDF-dokumentet

Slutligen, när allt är konfigurerat, kan du spara PDF-dokumentet på önskad plats.

```csharp
// Definiera utdatafilens sökväg
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// Spara PDF-dokumentet
pdfDocument.Save(dataDir);

// Bekräfta framgångsrikt skapande
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

Och det är det! Du har framgångsrikt skapat en PDF med grupperade kryssrutor med Aspose.PDF för .NET.

## Slutsats

Att lägga till interaktiva element som grupperade kryssrutor till PDF-dokument kan verka knepigt till en början, men med Aspose.PDF för .NET blir det enkelt. Genom att följa den här steg-för-steg-guiden har du lärt dig hur du skapar ett grundläggande PDF-dokument, lägger till grupperade alternativknappar, anpassar deras utseende och sparar det slutliga resultatet. Oavsett om du bygger formulär, undersökningar eller någon annan typ av interaktiv PDF, ger den här guiden dig en solid grund att börja med.

## FAQ's

### Kan jag lägga till fler än två alternativknappar i en grupp?
 Absolut! Instantiera helt enkelt ytterligare`RadioButtonOptionField` objekt och lägg till dem i`RadioButtonField` som visas i handledningen.

### Hur hanterar jag flera grupper av kryssrutor i ett dokument?
För att skapa flera grupper, instansiera separat`RadioButtonField` objekt för varje grupp.

### Finns det en gräns för antalet kryssrutor jag kan lägga till?
Nej, Aspose.PDF för .NET sätter inga begränsningar för antalet kryssrutor du kan lägga till i en PDF.

### Kan jag ändra utseendet på kryssrutorna efter att de har lagts till?
Ja, du kan ändra egenskaper som kantstil, bredd och färg efter att kryssrutorna har lagts till.

### Är det möjligt att använda bilder som radioknappar?
 Ja, Aspose.PDF låter dig använda anpassade bilder som radioknappar genom att ställa in`Appearance` egenskapen för varje alternativknapp.