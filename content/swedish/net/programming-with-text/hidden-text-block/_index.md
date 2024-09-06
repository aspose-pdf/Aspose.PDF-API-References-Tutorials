---
title: Dolt textblock i pdf-fil
linktitle: Dolt textblock i pdf-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du skapar dolda textblock i PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 230
url: /sv/net/programming-with-text/hidden-text-block/
---
den här handledningen kommer vi att förklara hur man skapar ett dolt textblock i PDF-fil med Aspose.PDF-biblioteket för .NET. Ett dolt textblock är en flytande text som blir synlig när muspekaren svävar över ett specifikt område. Vi kommer att gå igenom steg-för-steg-processen för att skapa det dolda textblocket med den medföljande C#-källkoden.

## Krav

Innan du börjar, se till att du har följande:

- Aspose.PDF för .NET-biblioteket installerat.
- En grundläggande förståelse för C#-programmering.

## Steg 1: Konfigurera dokumentkatalogen

 Först måste du ställa in sökvägen till katalogen där du vill spara den genererade PDF-filen. Ersätta`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till din önskade katalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett exempeldokument

I det här steget skapar vi ett exempel på PDF-dokument och lägger till ett textfragment till det. Textfragmentet kommer att fungera som utlösaren för att visa det dolda textblocket.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Steg 3: Öppna dokumentet

 Nu öppnar vi det tidigare skapade dokumentet med hjälp av`Document` klass.

```csharp
Document document = new Document(outputFile);
```

## Steg 4: Hitta textfragmentet

 Vi använder a`TextFragmentAbsorber`objekt för att hitta textfragmentet som kommer att utlösa visningen av det dolda textblocket. I det här fallet söker vi efter den exakta texten "Flytta muspekaren hit för att visa flytande text".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Steg 5: Skapa det dolda textfältet

 Vi skapar en`TextBoxField` objekt för att representera det dolda textfältet. Detta fält kommer att innehålla texten som blir synlig när muspekaren svävar över triggertexten.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Steg 6: Lägg till det dolda textfältet i dokumentet

Vi lägger till det dolda textfältet i dokumentets formulärsamling.

```csharp
document.Form.Add(floatingField);
```

## Steg 7: Skapa den osynliga knappen

Vi skapar ett osynligt knappfält som kommer att placeras ovanpå triggertextfragmentet. Detta knappfält kommer att ha åtgärder associerade med musentré- och utgångshändelser.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Steg 8: Spara dokumentet

Slutligen sparar vi det ändrade dokumentet med det dolda textblocket.

```csharp
document. Save(outputFile);
```

### Exempel på källkod för Hidden Text Block med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Skapa exempeldokument med text
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Öppna dokument med text
Document document = new Document(outputFile);
// Skapa TextAbsorber-objekt för att hitta alla fraser som matchar det reguljära uttrycket
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Acceptera absorbenten för dokumentsidorna
document.Pages.Accept(absorber);
// Hämta det första extraherade textfragmentet
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//Skapa dolt textfält för flytande text i den angivna rektangeln på sidan
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Ställ in text som ska visas som fältvärde
floatingField.Value = "This is the \"floating text field\".";
// Vi rekommenderar att du gör fältet "skrivskyddat" för detta scenario
floatingField.ReadOnly = true;
// Ställ in "dold" flagga för att göra fält osynligt när dokument öppnas
floatingField.Flags |= AnnotationFlags.Hidden;
// Att ange ett unikt fältnamn är inte nödvändigt men tillåtet
floatingField.PartialName = "FloatingField_1";
// Att ställa in egenskaper för fältutseende är inte nödvändigt men gör det bättre
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Lägg till textfält i dokumentet
document.Form.Add(floatingField);
// Skapa osynlig knapp på textfragmentposition
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Skapa ny gömma åtgärd för specificerat fält (anteckning) och osynlighetsflagga.
// (Du kan också hänvisa till flytande fält med namnet om du angav det ovan.)
// Lägg till åtgärder på musen enter/exit vid det osynliga knappfältet
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Lägg till knappfält i dokumentet
document.Form.Add(buttonField);
// Spara dokument
document.Save(outputFile);
```

## Slutsats

den här handledningen har du lärt dig hur du skapar ett dolt textblock med Aspose.PDF för .NET-biblioteket. Genom att följa steg-för-steg-guiden kan du skapa ett PDF-dokument med ett dolt textfält som blir synligt när muspekaren svävar över ett specifikt område. Du kan anpassa utseendet och beteendet för det dolda textblocket enligt dina krav.

### FAQ's

#### F: Vad är syftet med handledningen "Dold textblock i PDF-fil"?

S: Handledningen "Dold textblock i PDF-fil" förklarar hur man skapar ett dolt textblock i en PDF-fil med Aspose.PDF-biblioteket för .NET. Ett dolt textblock är en flytande text som blir synlig när muspekaren svävar över ett specifikt område. Denna handledning ger en steg-för-steg-guide med C#-källkod.

#### F: Varför skulle jag vilja skapa ett dolt textblock i en PDF-fil?

S: Att skapa ett dolt textblock kan vara användbart för interaktiva PDF-dokument där du vill ge ytterligare information eller sammanhang som bara blir synligt när en användare för muspekaren över ett angivet område.

#### F: Hur ställer jag in dokumentkatalogen?

S: Så här ställer du in dokumentkatalogen:

1.  Ersätta`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till katalogen där du vill spara den genererade PDF-filen.

#### F: Hur skapar jag ett exempeldokument och lägger till ett textfragment till det?

 S: I handledningen använder du`Document` klass för att skapa ett exempel på PDF-dokument och lägga till ett textfragment. Detta textfragment fungerar som utlösaren för att visa det dolda textblocket.

#### F: Hur hittar jag textfragmentet som utlöser det dolda textblocket?

 S: Handledningen visar hur man använder en`TextFragmentAbsorber` objekt för att hitta textfragmentet som utlöser visningen av det dolda textblocket. Den söker efter en specifik textsträng i PDF-dokumentet.

#### F: Hur skapar och anpassar jag det dolda textfältet?

 A: Du skapar en`TextBoxField`objekt för att representera det dolda textfältet. Handledningen tillhandahåller kod för att ställa in olika egenskaper som position, värde, utseende och beteende för det dolda textfältet.

#### F: Hur skapar jag en osynlig knapp kopplad till det dolda textblocket?

 S: Ett osynligt knappfält skapas med hjälp av`ButtonField` klass. Det här knappfältet är placerat ovanpå triggertextfragmentet och har åtgärder associerade med musentré- och utgångshändelser. Dessa åtgärder styr synligheten för det dolda textblocket.

#### F: Kan jag anpassa utseendet på det dolda textblocket och triggerområdet?

S: Ja, du kan anpassa olika egenskaper för både det dolda textfältet och den osynliga knappen, inklusive teckensnitt, färg, storlek och placering.

#### F: Hur sparar jag det ändrade dokumentet med det dolda textblocket?

 S: Handledningen visar hur man sparar det ändrade dokumentet med hjälp av`Save` metod för`Document` klass.