---
title: Inline strukturelement
linktitle: Inline strukturelement
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att använda online-strukturelement med Aspose.PDF för .NET. Organisera dina PDF-filer med rubriker och stycken.
type: docs
weight: 110
url: /sv/net/programming-with-tagged-pdf/inline-structure-elements/
---
den här steg-för-steg-guiden visar vi dig hur du använder inline-strukturelement med Aspose.PDF för .NET. Aspose.PDF är ett kraftfullt bibliotek som låter dig manipulera PDF-dokument programmatiskt. Inline-strukturelement låter dig skapa en hierarkisk struktur i ditt PDF-dokument med hjälp av rubriker på olika nivåer och stycken.

Låt oss dyka in i koden och lära oss hur man använder inline-strukturelement med Aspose.PDF för .NET.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Aspose.PDF-bibliotek för .NET installerat.
2. Grundläggande kunskaper i programmeringsspråket C#.

## Steg 1: Sätta upp miljön

För att komma igång, öppna din C#-utvecklingsmiljö och skapa ett nytt projekt. Se till att du har lagt till en referens till Aspose.PDF-biblioteket för .NET i ditt projekt.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa dokumentet

 Det första steget är att skapa ett nytt PDF-dokument med hjälp av`Document` klass.

```csharp
// Skapa PDF-dokumentet
Document document = new Document();
```

## Steg 3: Arbeta med taggat innehåll

Sedan får vi det taggade innehållet i dokumentet att arbeta med.

```csharp
// Hämta det taggade innehållet i dokumentet
ITaggedContent taggedContent = document.TaggedContent;
```

## Steg 4: Ställ in dokumentets titel och språk

Vi kan nu ställa in dokumentets titel och språk.

```csharp
// Definiera dokumentets titel och språk
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Steg 5: Lägg till strukturella element online

Nu ska vi lägga till inline-strukturelement som rubriker på olika nivåer och stycken i vårt dokument.

```csharp
// Hämta rotstrukturelementet
StructureElement rootElement = taggedContent.RootElement;

// Lägg till rubriker på olika nivåer
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Lägg till innehåll i varje rubrik
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Lägg till ett stycke
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Lägg till innehåll i stycket
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Här skapar vi inline-strukturelement, såsom rubriker på olika nivåer och ett stycke, och lägger till innehåll till dem.

## Steg 6: Spara det taggade PDF-dokumentet

Slutligen sparar vi det taggade PDF-dokumentet.

```csharp
// Spara det taggade PDF-dokumentet
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Exempel på källkod för Inline Structure Elements med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Skapa pdf-dokument
Document document = new Document();

// Skaffa innehåll för arbetet med TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Ställ in titel och språk för Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Skaffa rotstrukturelement
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Spara taggat pdf-dokument
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Slutsats

Grattis! Du har lärt dig hur man använder inline-strukturelement med Aspose.PDF för .NET. Du kan nu skapa en hierarkisk struktur i ditt PDF-dokument genom att använda rubriker på olika nivåer och stycken. Utforska fler funktioner i Aspose.PDF för att upptäcka dess fulla potential.

### FAQ's

#### F: Vad är inline-strukturelement i ett PDF-dokument, och hur bidrar de till att skapa en hierarkisk struktur?

S: Inline-strukturelement i ett PDF-dokument, såsom rubriker på olika nivåer och stycken, används för att skapa en hierarkisk struktur som organiserar och presenterar innehåll på ett strukturerat sätt. Dessa element gör att du kan skapa en tydlig hierarki och informationsflöde i dokumentet.

#### F: Hur kan inline-strukturelement förbättra läsbarheten och organisationen av ett PDF-dokument?

S: Inline-strukturelement, särskilt rubriker och stycken, hjälper till att förbättra läsbarheten och organisationen av ett PDF-dokument genom att tillhandahålla en logisk struktur. Rubriker indikerar olika nivåer av betydelse och hjälper läsarna att navigera i innehållet, medan stycken grupperar relaterad information.

#### F: Hur underlättar Aspose.PDF för .NET användningen av inline-strukturelement?

S: Aspose.PDF för .NET erbjuder klasser och metoder för att skapa och manipulera inline-strukturelement, såsom rubriker och stycken. Dessa element kan anpassas, organiseras hierarkiskt och berikas med innehåll för att förbättra den visuella presentationen och tillgängligheten för dokumentet.

####  F: Vad är syftet med`taggedContent` object in relation to inline structure elements?

 A: Den`taggedContent` föremål, erhållet från`TaggedContent` egendom hos en`Document`, låter dig arbeta med strukturerade element, inklusive inline-strukturelement. Det låter dig skapa, anpassa och organisera rubriker och stycken i dokumentet.

#### F: Hur hjälper inline-strukturelement till att skapa en tydlig dokumenthierarki?

S: Inline strukturelement, såsom rubriker på olika nivåer, bidrar till att upprätta en tydlig och väldefinierad hierarki i dokumentet. Läsare kan snabbt identifiera huvudämnena, underämnen och relaterat innehåll, vilket gör dokumentet lättare att navigera och förstå.

#### F: Kan jag anpassa utseendet och formateringen av inline-strukturelement med Aspose.PDF för .NET?

S: Ja, du kan anpassa utseendet och formateringen av inline-strukturelement. Du kan ställa in egenskaper som typsnittsstilar, storlekar, färger, justering, indrag och mellanrum för att uppnå önskad visuell presentation för rubriker och stycken.

#### F: Hur skapar och lägger jag till rubriker på olika nivåer i ett PDF-dokument med inline-strukturelement i Aspose.PDF för .NET?

 S: Du kan skapa rubriker på olika nivåer med hjälp av`CreateHeaderElement` metod och sedan lägga till dem till rotstrukturelementet. Därefter kan du lägga till innehåll till varje rubrikelement med hjälp av`CreateSpanElement` metod för att skapa spann av text.

#### F: Kan jag använda inline-strukturelement för att skapa listor, punktpunkter eller andra typer av innehållsorganisation i ett PDF-dokument?

S: Även om själva inline-strukturelementen i första hand används för rubriker och stycken, kan du använda dem i kombination med andra funktioner som erbjuds av Aspose.PDF för .NET för att skapa listor, punktpunkter, tabeller och andra typer av innehållsorganisation för en heltäckande dokumentstruktur.

#### F: Hur bidrar inline-strukturelement till dokumenttillgänglighet?

S: Inline-strukturelement spelar en avgörande roll för att förbättra dokumenttillgängligheten. Korrekt strukturerade rubriker och stycken ger en tydlig dokumenthierarki som hjälper skärmläsare och andra hjälpmedelstekniker att korrekt tolka och förmedla innehållet till användare med funktionshinder.

#### F: Kan jag utforska mer avancerad användning av inline-strukturelement, som att skapa interaktiva element eller bädda in multimedia?

A: Absolut! Medan den här handledningen fokuserar på att skapa rubriker och stycken, erbjuder Aspose.PDF för .NET avancerade funktioner för att skapa interaktiva element, bädda in multimedia, lägga till hyperlänkar och mer. Kontrollera bibliotekets dokumentation och exempel för att fördjupa dig i dessa avancerade funktioner.