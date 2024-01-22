---
title: Sök text och lägg till hyperlänk
linktitle: Sök text och lägg till hyperlänk
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du söker efter text i en PDF, lägger till hyperlänkar till den hittade texten och sparar det modifierade dokumentet med Aspose.PDF för .NET.
type: docs
weight: 450
url: /sv/net/programming-with-text/search-text-and-add-hyperlink/
---
Denna handledning förklarar hur du använder Aspose.PDF för .NET för att söka efter specifik text i ett PDF-dokument, lägga till en hyperlänk till den hittade texten och spara det ändrade dokumentet. Den medföljande C#-källkoden demonstrerar processen steg för steg.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Steg 3: Ställ in sökvägen till dokumentkatalogen

 Ställ in sökvägen till din dokumentkatalog med hjälp av`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Skapa en TextFragmentAbsorber

 Skapa en`TextFragmentAbsorber` objekt för att hitta alla instanser av den inmatade sökfrasen:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Byta ut`"\\d{4}-\\d{4}"` med ditt önskade reguljära uttrycksmönster.

## Steg 5: Aktivera sökning i reguljära uttryck

 Aktivera sökning efter reguljära uttryck genom att ställa in`TextSearchOptions` absorbatorns egenskaper:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Steg 6: Öppna och bind PDF-dokumentet

 Skapa en`PdfContentEditor` objekt och binda det till käll-PDF-filen:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Byta ut`"SearchRegularExpressionPage.pdf"` med det faktiska namnet på din PDF-fil.

## Steg 7: Acceptera absorbenten för sidan

Acceptera absorbenten för önskad sida i dokumentet:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Byta ut`1` med önskat sidnummer.

## Steg 8: Lägg till hyperlänkar till den hittade texten

Gå igenom de hämtade textfragmenten och lägg till hyperlänkar till dem:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Skapa en rektangel baserat på textfragmentets position
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Lägg till en webblänk till rektangeln
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Byta ut`"http://www.aspose.com"` med önskad hyperlänk-URL.

## Steg 9: Spara och stäng det ändrade dokumentet

Spara det ändrade dokumentet och stäng redigeraren:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Se till att byta ut`"SearchTextAndAddHyperlink_out.pdf"` med önskat utdatafilnamn.

### Exempel på källkod för söktext och lägg till hyperlänk med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Skapa absorberobjekt för att hitta alla instanser av den inmatade sökfrasen
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Aktivera sökning i reguljära uttryck
absorber.TextSearchOptions = new TextSearchOptions(true);
// Öppna dokumentet
PdfContentEditor editor = new PdfContentEditor();
// Bind käll PDF-fil
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Acceptera absorbenten för sidan
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Gå igenom fragmenten
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, blå, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du söker efter specifik text i ett PDF-dokument, lägger till hyperlänkar till den hittade texten och sparar det modifierade dokumentet med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att ställa in projektet till att utföra de nödvändiga åtgärderna. Du kan nu infoga den här koden i dina egna C#-projekt för att manipulera text och lägga till hyperlänkar i PDF-filer.

### FAQ's

#### F: Vad är syftet med handledningen "Sök text och lägg till hyperlänk"?

S: Handledningen "Sök text och lägg till hyperlänk" syftar till att visa hur man använder Aspose.PDF-biblioteket för .NET för att söka efter specifik text i ett PDF-dokument, lägga till hyperlänkar till den hittade texten och sedan spara det ändrade dokumentet. Handledningen tillhandahåller en omfattande guide och C#-kodexempel för att illustrera processen steg-för-steg.

#### F: Hur hjälper den här handledningen att lägga till hyperlänkar till specifik text i ett PDF-dokument?

S: Denna handledning guidar dig genom processen att använda Aspose.PDF-biblioteket för att hitta specifik text i ett PDF-dokument, lägga till en hyperlänk på den identifierade texten och spara den ändrade PDF-filen. Den täcker viktiga steg som att ställa in projektet, ladda dokumentet, aktivera sökning i reguljära uttryck och lägga till hyperlänkar till den hittade texten.

#### F: Vilka förutsättningar krävs för att följa denna handledning?

S: Innan du börjar bör du ha en grundläggande förståelse för programmeringsspråket C#. Dessutom måste du ha Aspose.PDF för .NET-biblioteket installerat, som kan erhållas från Asposes webbplats eller installeras med NuGet i ditt projekt.

#### F: Hur ställer jag in mitt projekt för att följa denna handledning?

S: Börja med att skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE). Lägg sedan till en referens till Aspose.PDF för .NET-biblioteket, vilket gör att du kan använda bibliotekets kapacitet i ditt projekt.

#### F: Kan jag lägga till hyperlänkar till specifik text med den här handledningen?

S: Ja, den här handledningen fokuserar specifikt på att lägga till hyperlänkar till specifik text i ett PDF-dokument. Den visar hur man hittar och extraherar önskad text med hjälp av reguljära uttryck, skapar hyperlänkar associerade med textfragmenten och sparar den modifierade PDF-filen.

#### F: Hur definierar jag texten jag vill söka efter och lägger till en hyperlänk till?

 S: För att ange texten du vill söka efter och lägga till en hyperlänk till, skapa en`TextFragmentAbsorber` objekt och ställ in dess mönster med hjälp av`Text` parameter. Byt ut standardmönstret`"\\d{4}-\\d{4}"` i handledningens kod med ditt önskade reguljära uttrycksmönster.

#### F: Hur kan jag aktivera reguljära uttryckssökning efter text?

 S: Reguljära uttryckssökning aktiveras genom att skapa en`TextSearchOptions` objekt och ställer in dess värde till`true` . Tilldela detta objekt till`TextSearchOptions` egendom av`TextFragmentAbsorber` exempel. Detta säkerställer att det reguljära uttrycksmönstret tillämpas under textsökning.

#### F: Hur lägger jag till hyperlänkar till den hittade texten?

 S: Efter att ha identifierat textfragmenten med hjälp av`TextFragmentAbsorber` , ger handledningen en loop för att iterera genom dessa fragment. För varje textfragment visar handledningen hur man ställer in textfärgen till blå och skapar en hyperlänk med hjälp av`CreateWebLink` metod.

#### F: Vilka är stegen för att spara den modifierade PDF-filen med hyperlänkar?

 S: När du har lagt till hyperlänkar till de önskade textfragmenten, använd`PdfContentEditor` klass för att spara det ändrade dokumentet. Handledningens exempelkod visar hur du sparar den redigerade PDF-filen, stänger redigeraren och visar ett lyckat meddelande.