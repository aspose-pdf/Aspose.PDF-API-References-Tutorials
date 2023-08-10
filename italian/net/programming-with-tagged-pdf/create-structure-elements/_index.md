---
title: Crea elementi della struttura
linktitle: Crea elementi della struttura
second_title: Aspose.PDF per riferimento API .NET
description: In questo tutorial imparerai come utilizzare Aspose.PDF per .NET per creare elementi strutturali in un documento PDF con tag.
type: docs
weight: 60
url: /it/net/programming-with-tagged-pdf/create-structure-elements/
---
Il seguente codice sorgente C# usa Aspose.PDF per .NET per creare elementi della struttura. Segui i passaggi seguenti per capire come funziona il codice.

## Passaggio 1: importa le librerie necessarie

```csharp
using Aspose.Pdf;
```

## Passo 2: Definisci la directory dei tuoi documenti

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assicurati di specificare il percorso corretto della directory dei documenti.

## Passaggio 3: creare un documento PDF

```csharp
Document document = new Document();
```

Creiamo un nuovo oggetto Document che rappresenta il documento PDF.

## Passaggio 4: fai in modo che i contenuti funzionino con TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Recuperiamo il contenuto con tag del documento PDF. Questo ci permetterà di manipolare gli elementi strutturali.

## Passaggio 5: imposta il titolo e la lingua del documento

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Impostiamo il titolo e la lingua del documento PDF con tag. Ciò migliora l'accessibilità del documento.

## Passaggio 6: creare elementi di raggruppamento

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

Creiamo diversi elementi strutturali per raggruppare i contenuti nel documento PDF.

## Passaggio 7: creare elementi della struttura del paragrafo

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Creiamo elementi strutturali a livello di blocco per paragrafi e intestazioni. L'esempio sopra mostra la creazione di un'intestazione di livello 1.

## Passaggio 8: creare elementi di struttura a livello in linea

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Creiamo elementi di struttura a livello in linea per le parti di testo che appaiono all'interno di un paragrafo o di un'intestazione.

## Passaggio 9: creare elementi della struttura grafica

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Creiamo elementi strutturali per le illustrazioni e le formule matematiche presenti nel documento.

## Passaggio 10: salvare il documento PDF con tag

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Salviamo il documento PDF con tag con gli elementi della struttura creati.

### Esempio di codice sorgente per Crea elementi di struttura utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea documento Pdf
Document document = new Document();
// Ottieni contenuti per lavorare con TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Imposta titolo e lingua per il documento
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Crea elementi di raggruppamento
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
// Crea elementi di struttura a livello di blocco di testo
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Crea elementi di struttura a livello di testo in linea
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Crea elementi della struttura dell'illustrazione
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// I metodi sono in fase di sviluppo
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
// Salva documento PDF con tag
document.Save(dataDir + "StructureElements.pdf");

```

## Conclusione

In questo tutorial, abbiamo imparato come utilizzare Aspose.PDF per .NET per creare elementi di struttura in un documento PDF con tag. Gli elementi strutturali aiutano a migliorare l'accessibilità dei documenti e a organizzare i contenuti in modo significativo. Ora puoi usare questa conoscenza per creare documenti PDF strutturati e facili da navigare.

### FAQ

#### D: Qual è lo scopo della creazione di elementi di struttura in un documento PDF utilizzando Aspose.PDF per .NET?

R: Creazione di elementi di struttura in un documento PDF utilizzando Aspose.PDF per .NET migliora l'accessibilità e l'organizzazione del contenuto del documento. Gli elementi della struttura forniscono una struttura gerarchica che migliora la navigazione, la semantica e la compatibilità con le tecnologie assistive.

#### D: In che modo il codice C# fornito crea elementi di struttura in un documento PDF?

R: L'esempio di codice mostra come creare vari tipi di elementi della struttura, inclusi elementi di raggruppamento (come parti, sezioni e div), elementi a livello di blocco (come paragrafi e intestazioni), elementi a livello di riga (span, quote, note ) ed elementi grafici (come figure e formule). Questi elementi della struttura aiutano a organizzare il contenuto.

####  D: Perché è importante impostare il titolo e la lingua del documento utilizzando il`SetTitle` and `SetLanguage` methods?

 R: Impostare il titolo e la lingua del documento utilizzando il file`SetTitle` E`SetLanguage`metodi migliora l'accessibilità e la semantica dei documenti. Il titolo fornisce una breve descrizione dello scopo del documento, mentre l'attributo language migliora la resa e l'accessibilità specifiche della lingua.

####  D: Come raggruppare gli elementi, ad esempio`PartElement` and `SectElement`, contribute to the structure of the PDF document?

R: Gli elementi di raggruppamento creano una struttura gerarchica all'interno del documento PDF, consentendo di organizzare e raggruppare logicamente i contenuti correlati. Ciò migliora la navigazione e fornisce una struttura chiara per gli utenti.

#### D: Cosa sono gli elementi della struttura a livello di blocco e in linea e in che cosa differiscono?

R: Gli elementi della struttura a livello di blocco rappresentano blocchi di contenuto più grandi, come paragrafi e intestazioni, mentre gli elementi a livello di riga rappresentano parti di testo all'interno di un paragrafo o di un'intestazione, come intervalli, virgolette e note. Aiutano a definire la gerarchia e le relazioni dei contenuti.

####  D: In che modo gli elementi della struttura grafica, come`FigureElement` and `FormulaElement`, contribute to the document?

R: Gli elementi della struttura grafica consentono di aggiungere illustrazioni, figure e formule matematiche al documento. Forniscono un modo strutturato per includere contenuti visivi e matematici.

#### D: Posso utilizzare tecniche simili per creare altri tipi di elementi della struttura, come elenchi, tabelle o annotazioni?

R: Sì, puoi utilizzare tecniche simili per creare altri tipi di elementi della struttura come elenchi, tabelle, annotazioni, riferimenti e altro. Aspose.PDF fornisce una vasta gamma di metodi di creazione di elementi di struttura.

####  D: In che modo salvare il documento PDF con tag utilizzando il file`Save` method ensure the preservation of structure elements?

 R: Il`Save` Il metodo salva il documento PDF insieme agli elementi della struttura creati, assicurando che la struttura gerarchica e semantica del documento sia preservata per l'accessibilità e la navigazione.

#### D: Quali vantaggi apportano gli elementi della struttura ai documenti PDF in termini di accessibilità e compatibilità con le tecnologie assistive?

R: Gli elementi della struttura migliorano l'accessibilità fornendo una struttura e una semantica significative al documento. Ciò consente alle tecnologie assistive come i lettori di schermo di interpretare e trasmettere il contenuto del documento in modo più efficace agli utenti con disabilità.

#### D: Come posso personalizzare ulteriormente e combinare diversi tipi di elementi della struttura nei miei documenti PDF?

A: È possibile combinare e personalizzare gli elementi della struttura utilizzando i metodi di creazione appropriati forniti da Aspose.PDF. Sperimenta con diversi elementi e le loro proprietà per creare un documento PDF ben strutturato e organizzato.