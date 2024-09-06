---
title: Crea elementi di struttura
linktitle: Crea elementi di struttura
second_title: Riferimento API Aspose.PDF per .NET
description: In questo tutorial imparerai come utilizzare Aspose.PDF per .NET per creare elementi strutturali in un documento PDF taggato.
type: docs
weight: 60
url: /it/net/programming-with-tagged-pdf/create-structure-elements/
---
Il seguente codice sorgente C# usa Aspose.PDF per .NET per creare elementi di struttura. Segui i passaggi sottostanti per capire come funziona il codice.

## Passaggio 1: importare le librerie necessarie

```csharp
using Aspose.Pdf;
```

## Passaggio 2: definisci la directory dei tuoi documenti

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assicuratevi di specificare il percorso corretto per la directory dei vostri documenti.

## Passaggio 3: creare un documento PDF

```csharp
Document document = new Document();
```

Creiamo un nuovo oggetto Documento che rappresenta il documento PDF.

## Passaggio 4: Ottieni il contenuto per lavorare con TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Recuperiamo il contenuto taggato del documento PDF. Questo ci consentirà di manipolare gli elementi strutturali.

## Passaggio 5: impostare il titolo e la lingua del documento

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Impostiamo il titolo e la lingua del documento PDF taggato. Ciò migliora l'accessibilità del documento.

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

Creiamo elementi strutturali a livello di blocco per paragrafi e titoli. L'esempio sopra mostra la creazione di un titolo di livello 1.

## Passaggio 8: creare elementi di struttura di livello in linea

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Creiamo elementi di struttura di livello in linea per le parti di testo che compaiono all'interno di un paragrafo o di un titolo.

## Passaggio 9: creare elementi della struttura dell'opera d'arte

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Creiamo elementi strutturali per le illustrazioni e le formule matematiche presenti nel documento.

## Passaggio 10: Salvare il documento PDF taggato

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Salviamo il documento PDF taggato con gli elementi della struttura creati.

### Esempio di codice sorgente per creare elementi di struttura utilizzando Aspose.PDF per .NET 

```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea documento PDF
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
// Creare elementi di struttura a livello di blocco di testo
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Creare elementi di struttura di testo a livello in linea
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Crea elementi di struttura dell'illustrazione
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
// Salva il documento PDF taggato
document.Save(dataDir + "StructureElements.pdf");

```

## Conclusione

In questo tutorial, abbiamo imparato come usare Aspose.PDF per .NET per creare elementi di struttura in un documento PDF taggato. Gli elementi strutturali aiutano a migliorare l'accessibilità del documento e a organizzare il contenuto in modo significativo. Ora puoi usare questa conoscenza per creare documenti PDF strutturati e facili da navigare.

### Domande frequenti

#### D: Qual è lo scopo della creazione di elementi di struttura in un documento PDF utilizzando Aspose.PDF per .NET?

A: La creazione di elementi di struttura in un documento PDF tramite Aspose.PDF per .NET migliora l'accessibilità e l'organizzazione del contenuto del documento. Gli elementi di struttura forniscono una struttura gerarchica che migliora la navigazione, la semantica e la compatibilità con le tecnologie assistive.

#### D: In che modo il codice C# fornito crea elementi di struttura in un documento PDF?

R: L'esempio di codice dimostra come creare vari tipi di elementi di struttura, tra cui elementi di raggruppamento (come parti, sezioni e div), elementi a livello di blocco (come paragrafi e titoli), elementi a livello in linea (span, citazione, nota) ed elementi di grafica (come figure e formule). Questi elementi di struttura aiutano a organizzare il contenuto.

####  D: Perché è importante impostare il titolo e la lingua del documento utilizzando`SetTitle` and `SetLanguage` methods?

 A: Impostazione del titolo e della lingua del documento utilizzando`SetTitle` E`SetLanguage`methods migliora l'accessibilità e la semantica del documento. Il titolo fornisce una breve descrizione dello scopo del documento, mentre l'attributo language migliora il rendering e l'accessibilità specifici della lingua.

####  D: Come vengono raggruppati gli elementi, come`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Gli elementi di raggruppamento creano una struttura gerarchica all'interno del documento PDF, consentendo di organizzare e raggruppare logicamente i contenuti correlati. Ciò migliora la navigazione e fornisce una struttura chiara per gli utenti.

#### D: Cosa sono gli elementi di struttura a livello di blocco e a livello inline e in che modo differiscono?

A: Gli elementi di struttura a livello di blocco rappresentano blocchi di contenuto più grandi, come paragrafi e titoli, mentre gli elementi a livello in linea rappresentano parti di testo all'interno di un paragrafo o titolo, come intervalli, citazioni e note. Aiutano a definire la gerarchia e le relazioni del contenuto.

####  D: In che modo gli elementi della struttura artistica, come`FigureElement` and `FormulaElement`, contribute to the document?

A: Gli elementi di struttura dell'artwork consentono di aggiungere illustrazioni, figure e formule matematiche al documento. Forniscono un modo strutturato per includere contenuti visivi e matematici.

#### D: Posso utilizzare tecniche simili per creare altri tipi di elementi strutturali, come elenchi, tabelle o annotazioni?

R: Sì, puoi usare tecniche simili per creare altri tipi di elementi di struttura come elenchi, tabelle, annotazioni, riferimenti e altro. Aspose.PDF fornisce un'ampia gamma di metodi di creazione di elementi di struttura.

####  D: Come funziona il salvataggio del documento PDF taggato utilizzando`Save` method ensure the preservation of structure elements?

 A: Il`Save` Il metodo salva il documento PDF insieme agli elementi della struttura creati, garantendo che la struttura gerarchica e semantica del documento venga preservata per garantire accessibilità e navigazione.

#### D: Quali vantaggi apportano gli elementi strutturali ai documenti PDF in termini di accessibilità e compatibilità con le tecnologie assistive?

A: Gli elementi di struttura migliorano l'accessibilità fornendo una struttura e una semantica significative al documento. Ciò consente alle tecnologie assistive come gli screen reader di interpretare e trasmettere il contenuto del documento in modo più efficace agli utenti con disabilità.

#### D: Come posso personalizzare e combinare ulteriormente i diversi tipi di elementi strutturali nei miei documenti PDF?

A: Puoi combinare e personalizzare gli elementi della struttura utilizzando i metodi di creazione appropriati forniti da Aspose.PDF. Sperimenta con diversi elementi e le loro proprietà per creare un documento PDF ben strutturato e organizzato.