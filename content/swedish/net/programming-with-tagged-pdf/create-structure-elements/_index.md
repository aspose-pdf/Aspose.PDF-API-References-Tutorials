---
title: Skapa strukturelement
linktitle: Skapa strukturelement
second_title: Aspose.PDF för .NET API-referens
description: I den här handledningen kommer du att lära dig hur du använder Aspose.PDF för .NET för att skapa strukturella element i ett taggat PDF-dokument.
type: docs
weight: 60
url: /sv/net/programming-with-tagged-pdf/create-structure-elements/
---
Följande C#-källkod använder Aspose.PDF för .NET för att skapa strukturelement. Följ stegen nedan för att förstå hur koden fungerar.

## Steg 1: Importera nödvändiga bibliotek

```csharp
using Aspose.Pdf;
```

## Steg 2: Definiera katalogen för dina dokument

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Var noga med att ange rätt sökväg till din dokumentkatalog.

## Steg 3: Skapa ett PDF-dokument

```csharp
Document document = new Document();
```

Vi skapar ett nytt dokumentobjekt som representerar PDF-dokumentet.

## Steg 4: Få innehåll att fungera med TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Vi hämtar det taggade innehållet i PDF-dokumentet. Detta kommer att tillåta oss att manipulera strukturella element.

## Steg 5: Ställ in dokumentets titel och språk

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Vi anger titeln och språket för det taggade PDF-dokumentet. Detta förbättrar dokumentets tillgänglighet.

## Steg 6: Skapa grupperingselement

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

Vi skapar olika strukturella element för att gruppera innehåll i PDF-dokumentet.

## Steg 7: Skapa styckestrukturelement

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Vi skapar strukturella element på blocknivå för stycken och rubriker. Exemplet ovan visar skapandet av en nivå 1-rubrik.

## Steg 8: Skapa inline-nivåstrukturelement

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Vi skapar inline-nivåstrukturelement för de delar av text som förekommer i ett stycke eller en rubrik.

## Steg 9: Skapa konstverksstrukturelement

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Vi skapar strukturella element för de illustrationer och matematiska formler som finns i dokumentet.

## Steg 10: Spara det taggade PDF-dokumentet

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Vi sparar det taggade PDF-dokumentet med de skapade strukturelementen.

### Exempel på källkod för Skapa strukturelement med Aspose.PDF för .NET 

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
// Skapa grupperingselement
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Skapa strukturelement på textblocknivå
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Skapa text inline-nivå strukturelement
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Skapa illustrationsstrukturelement
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Metoder är under utveckling
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Spara taggat pdf-dokument
document.Save(dataDir + "StructureElements.pdf");

```

## Slutsats

I den här handledningen lärde vi oss hur man använder Aspose.PDF för .NET för att skapa strukturelement i ett taggat PDF-dokument. Strukturella element hjälper till att förbättra dokumenttillgängligheten och organisera innehåll på ett meningsfullt sätt. Nu kan du använda denna kunskap för att skapa strukturerade, lättnavigerade PDF-dokument.

### FAQ's

#### F: Vad är syftet med att skapa strukturelement i ett PDF-dokument med Aspose.PDF för .NET?

S: Att skapa strukturelement i ett PDF-dokument med Aspose.PDF för .NET förbättrar tillgängligheten och organisationen av dokumentets innehåll. Strukturelement ger en hierarkisk struktur som förbättrar navigering, semantik och kompatibilitet med hjälpmedelstekniker.

#### F: Hur skapar den medföljande C#-koden strukturelement i ett PDF-dokument?

S: Kodexemplet visar hur man skapar olika typer av strukturelement, inklusive grupperingselement (som delar, sektioner och div), element på blocknivå (som stycken och rubriker), element på inlinenivå (span, citat, not ), och konstverk (som figurer och formler). Dessa strukturelement hjälper till att organisera innehåll.

####  F: Varför är det viktigt att ställa in dokumentets titel och språk med hjälp av`SetTitle` and `SetLanguage` methods?

 S: Ställa in dokumentets titel och språk med hjälp av`SetTitle` och`SetLanguage`metoder förbättrar dokumenttillgänglighet och semantik. Titeln ger en kort beskrivning av dokumentets syfte, medan språkattributet förbättrar språkspecifik rendering och tillgänglighet.

####  F: Hur fungerar gruppering av element, som t.ex`PartElement` and `SectElement`, contribute to the structure of the PDF document?

S: Grupperingselement skapar en hierarkisk struktur i PDF-dokumentet, så att du logiskt kan organisera och gruppera relaterat innehåll. Detta förbättrar navigeringen och ger en tydlig struktur för användarna.

#### F: Vad är strukturelement på blocknivå och inlinenivå, och hur skiljer de sig åt?

S: Strukturelement på blocknivå representerar större innehållsblock, som stycken och rubriker, medan element på radnivå representerar delar av text i ett stycke eller en rubrik, som intervall, citat och anteckningar. De hjälper till att definiera hierarkin och relationerna mellan innehåll.

####  F: Hur strukturerar konstverk element, som`FigureElement` and `FormulaElement`, contribute to the document?

S: Konstverksstrukturelement låter dig lägga till illustrationer, figurer och matematiska formler till dokumentet. De ger ett strukturerat sätt att inkludera visuellt och matematiskt innehåll.

#### F: Kan jag använda liknande tekniker för att skapa andra typer av strukturelement, som listor, tabeller eller anteckningar?

S: Ja, du kan använda liknande tekniker för att skapa andra typer av strukturelement som listor, tabeller, anteckningar, referenser och mer. Aspose.PDF tillhandahåller ett brett utbud av metoder för att skapa strukturelement.

####  F: Hur fungerar det att spara det taggade PDF-dokumentet med hjälp av`Save` method ensure the preservation of structure elements?

 A: Den`Save` metoden sparar PDF-dokumentet tillsammans med de skapade strukturelementen, vilket säkerställer att dokumentets hierarkiska och semantiska struktur bevaras för tillgänglighet och navigering.

#### F: Vilka fördelar ger strukturelement till PDF-dokument när det gäller tillgänglighet och kompatibilitet med hjälpmedel?

S: Strukturelement förbättrar tillgängligheten genom att tillhandahålla en meningsfull struktur och semantik till dokumentet. Detta gör att hjälpmedel som skärmläsare kan tolka och förmedla dokumentets innehåll mer effektivt till användare med funktionshinder.

#### F: Hur kan jag ytterligare anpassa och kombinera olika typer av strukturelement i mina PDF-dokument?

S: Du kan kombinera och anpassa strukturelement genom att använda lämpliga skapandemetoder från Aspose.PDF. Experimentera med olika element och deras egenskaper för att skapa ett välstrukturerat och organiserat PDF-dokument.