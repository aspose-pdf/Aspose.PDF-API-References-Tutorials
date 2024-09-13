---
title: Horisontellt Och Vertikalt Radioknappar
linktitle: Horisontellt Och Vertikalt Radioknappar
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du skapar horisontellt och vertikalt justerade alternativknappar i PDF med Aspose.PDF för .NET med denna steg-för-steg handledning.
type: docs
weight: 180
url: /sv/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## Introduktion

Att skapa interaktiva PDF-formulär kan förbättra användarupplevelsen avsevärt, särskilt när det gäller att samla in information. Ett av de vanligaste formelementen är alternativknappen, som låter användare välja ett alternativ från en uppsättning. I den här handledningen kommer vi att utforska hur man skapar horisontellt och vertikalt justerade radioknappar med Aspose.PDF för .NET. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer den här guiden att leda dig genom processen steg-för-steg, vilket säkerställer att du har en tydlig förståelse för varje del.

## Förutsättningar

Innan du dyker in i koden finns det några förutsättningar du bör ha på plats:

1.  Aspose.PDF för .NET: Se till att du har Aspose.PDF-biblioteket installerat. Du kan ladda ner den från[plats](https://releases.aspose.com/pdf/net/).
2. Visual Studio: En utvecklingsmiljö där du kan skriva och testa din kod.
3. Grundläggande kunskaper i C#: Bekantskap med C#-programmering hjälper dig att förstå kodavsnitten bättre.

## Importera paket

För att komma igång måste du importera nödvändiga paket i ditt C#-projekt. Så här kan du göra det:

### Skapa ett nytt projekt

Öppna Visual Studio och skapa ett nytt C#-projekt. Du kan välja en konsolapplikation för enkelhetens skull.

### Lägg till Aspose.PDF-referens

1. Högerklicka på ditt projekt i Solution Explorer.
2. Välj "Hantera NuGet-paket."
3. Sök efter "Aspose.PDF" och installera den senaste versionen.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

Nu när du har allt inställt, låt oss dela upp koden för att skapa horisontellt och vertikalt justerade radioknappar.

## Steg 1: Konfigurera dokumentkatalogen

I det här steget kommer vi att definiera sökvägen till katalogen där dina PDF-dokument kommer att lagras.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen där du vill spara din PDF-fil. Detta är avgörande eftersom det talar om för programmet var det ska leta efter indatafiler och var det ska sparas.

## Steg 2: Ladda det befintliga PDF-dokumentet

 Därefter måste vi ladda PDF-dokumentet som vi kommer att arbeta med. Detta görs med hjälp av`FormEditor` klass.

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

Här skapar vi en instans av`FormEditor` och binda den till en befintlig PDF-fil med namnet`input.pdf`. Se till att den här filen finns i din angivna katalog.

## Steg 3: Konfigurera radioknappsegenskaper

Låt oss nu ställa in några egenskaper för våra radioknappar. Detta inkluderar gapet mellan knapparna, deras orientering och storlek.

```csharp
formEditor.RadioGap = 4; // Avstånd mellan alternativ för alternativknappar
formEditor.RadioHoriz = true; // Ställ in på sant för horisontell justering
formEditor.RadioButtonItemSize = 20; // Storlek på alternativknappen
formEditor.Facade.BorderWidth = 1; // Kantbredd
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Kantfärg
```

 Dessa egenskaper hjälper till att definiera hur alternativknapparna kommer att visas i PDF-filen. De`RadioGap` egenskapen styr utrymmet mellan knapparna, medan`RadioHoriz` bestämmer deras layout.

## Steg 4: Lägg till horisontella radioknappar

Låt oss nu lägga till de horisontella alternativknapparna till PDF:en.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

 I den här koden definierar vi objekten för alternativknapparna och lägger till dem i PDF:en. De`AddField`Metoden tar flera parametrar, inklusive fälttyp, fältnamn och koordinater för placering.

## Steg 5: Lägg till vertikala radioknappar

Därefter lägger vi till de vertikala radioknapparna. För att göra detta måste vi ändra orienteringen tillbaka till vertikal.

```csharp
formEditor.RadioHoriz = false; // Ställ in på false för vertikal justering
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

Precis som tidigare definierar vi objekten och lägger till dem i PDF:en, men den här gången kommer de att justeras vertikalt.

## Steg 6: Spara PDF-dokumentet

Slutligen måste vi spara det modifierade PDF-dokumentet.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

Denna kod sparar PDF-filen med de nyligen tillagda alternativknapparna. Se till att kontrollera den angivna katalogen för utdatafilen.

## Slutsats

Att skapa alternativknappar i en PDF med Aspose.PDF för .NET är en enkel process. Genom att följa stegen som beskrivs i denna handledning kan du enkelt lägga till både horisontellt och vertikalt justerade alternativknappar till dina PDF-formulär. Detta förbättrar inte bara interaktiviteten i dina dokument utan förbättrar också den övergripande användarupplevelsen. Så varsågod och prova!

## FAQ's

### Vad är Aspose.PDF för .NET?
Aspose.PDF för .NET är ett kraftfullt bibliotek som låter utvecklare skapa, manipulera och konvertera PDF-dokument programmatiskt.

### Kan jag använda Aspose.PDF gratis?
 Ja, Aspose erbjuder en gratis testversion som du kan använda för att utvärdera biblioteket. Du kan ladda ner den[här](https://releases.aspose.com/).

### Hur får jag support för Aspose.PDF?
 Du kan få stöd genom att besöka[Aspose forum](https://forum.aspose.com/c/pdf/10).

### Är det möjligt att skapa andra formulärelement med Aspose.PDF?
Absolut! Aspose.PDF stöder olika formulärelement, inklusive textfält, kryssrutor och rullgardinsmenyer.

### Var kan jag köpa Aspose.PDF för .NET?
 Du kan köpa Aspose.PDF för .NET från[köpsidan](https://purchase.aspose.com/buy).