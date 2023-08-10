---
title: Tagga l'immagine nel PDF esistente
linktitle: Tagga l'immagine nel PDF esistente
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come contrassegnare un'immagine in un PDF esistente con Aspose.PDF per .NET. Una guida passo passo per aggiungere tag alle immagini.
type: docs
weight: 210
url: /it/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
In questo tutorial dettagliato, ti guideremo passo dopo passo attraverso il codice sorgente C# fornito per contrassegnare un'immagine in un PDF esistente utilizzando Aspose.PDF per .NET. Segui le istruzioni di seguito per capire come aggiungere tag a un'immagine in un PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo per utilizzare Aspose.PDF per .NET. Ciò include l'installazione della libreria Aspose.PDF e la configurazione del progetto per farvi riferimento.

## Passaggio 2: aprire il documento PDF esistente

In questo passaggio, apriremo un documento PDF esistente utilizzando Aspose.PDF.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Percorsi dei file di input e output
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Apri il documento
Document document = new Document(inFile);
```

Abbiamo aperto il documento PDF esistente utilizzando Aspose.PDF.

## Passaggio 3: ottenere il contenuto con tag e l'elemento della struttura principale

Ora otterremo il contenuto con tag del documento PDF e il corrispondente elemento della struttura radice.

```csharp
// Ottieni il contenuto con tag e l'elemento della struttura principale
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Abbiamo ottenuto il contenuto con tag del documento PDF e il corrispondente elemento della struttura radice.

## Passaggio 4: impostazione del titolo per il documento PDF con tag

Ora impostiamo il titolo per il documento PDF con tag.

```csharp
// Definire il titolo per il documento PDF con tag
taggedContent.SetTitle("Document with images");
```

Abbiamo impostato il titolo per il documento PDF con tag.

## Passaggio 5: assegna i testi alternativi e il riquadro di delimitazione all'immagine

Ora, per ogni elemento dell'immagine, assegneremo un testo alternativo e un riquadro di delimitazione.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Assegna un testo alternativo all'immagine
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Crea e assegna il riquadro di delimitazione (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Abbiamo assegnato testo alternativo e un riquadro di delimitazione a ciascun elemento dell'immagine nel documento PDF.

## Passaggio 6: spostare l'elemento Span nel paragrafo

Ora spostiamo l'elemento Span nel paragrafo.

```csharp
// Sposta l'elemento Span nel paragrafo (trova span e paragrafo errati nel primo TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Sposta l'elemento Span nel paragrafo
spanElement.ChangeParentElement(paragraph);
```

Abbiamo spostato l'elemento Span nel paragrafo specificato.

## Passaggio 7: salvare il documento PDF modificato

Ora che abbiamo apportato le modifiche necessarie, salveremo il documento PDF modificato.

```csharp
// Salva il documento PDF
document. Save(outFile);
```

Abbiamo salvato il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per Tag Image In Existing PDF utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Apri documento
Document document = new Document(inFile);

// Ottiene il contenuto con tag e l'elemento della struttura radice
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Imposta il titolo per il documento pdf con tag
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Imposta testo alternativo per la figura
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Crea e imposta l'attributo BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Sposta elemento span in paragrafo (trova span e paragrafo errati nel primo TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Sposta l'elemento Span nel paragrafo
spanElement.ChangeParentElement(paragraph);

// Salva documento
document.Save(outFile);

//Controllo della conformità PDF/UA per il nostro documento
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusione

In questo tutorial, abbiamo imparato come contrassegnare un'immagine in un PDF esistente utilizzando Aspose.PDF per .NET. Ora puoi utilizzare Aspose.PDF per aggiungere tag e apportare modifiche alle immagini nei tuoi documenti PDF.

### FAQ

#### D: Qual è l'obiettivo principale di questo tutorial sull'etichettatura delle immagini in un PDF esistente utilizzando Aspose.PDF per .NET?

A: L'obiettivo principale di questo tutorial è guidarti attraverso il processo di contrassegno di un'immagine all'interno di un documento PDF esistente utilizzando Aspose.PDF per .NET. L'esercitazione fornisce istruzioni dettagliate ed esempi di codice sorgente C# per aiutarti a comprendere come assegnare testo alternativo e riquadri di delimitazione alle immagini, spostare elementi all'interno del documento e aggiungere tag alle immagini.

#### D: Quali sono i prerequisiti per seguire questo tutorial sull'etichettatura delle immagini in un PDF utilizzando Aspose.PDF per .NET?

R: Prima di iniziare, assicurati di aver impostato il tuo ambiente di sviluppo per utilizzare Aspose.PDF per .NET. Ciò comporta l'installazione della libreria Aspose.PDF e la configurazione del progetto per farvi riferimento.

#### D: Come posso aprire un documento PDF esistente e accedere al suo contenuto con tag utilizzando Aspose.PDF per .NET?

R: Il tutorial fornisce esempi di codice sorgente C# che dimostrano come aprire un documento PDF esistente utilizzando Aspose.PDF per .NET e accedere al suo contenuto con tag per ulteriori manipolazioni.

#### D: Qual è lo scopo dell'assegnazione di testo alternativo e riquadri di delimitazione alle immagini in un documento PDF?

R: L'assegnazione di testo alternativo e riquadri di delimitazione alle immagini migliora l'accessibilità fornendo testo descrittivo per le immagini e definendone il layout e la posizione all'interno del documento. Queste informazioni sono fondamentali per gli screen reader e altre tecnologie assistive.

#### D: Come posso impostare il titolo per un documento PDF con tag utilizzando Aspose.PDF per .NET?

R: Il tutorial include esempi di codice sorgente C# che illustrano come impostare il titolo per un documento PDF con tag utilizzando Aspose.PDF per .NET.

#### D: In cosa consiste il processo di spostamento degli elementi all'interno di un documento PDF?

R: Lo spostamento di elementi all'interno di un documento PDF comporta la modifica dell'elemento principale di un particolare elemento. In questo tutorial imparerai come spostare un elemento Span in un elemento Paragraph specificato all'interno di una tabella.

#### D: Come faccio a salvare il documento PDF modificato dopo aver aggiunto tag e apportato modifiche alle immagini?

 R: Dopo aver aggiunto tag, assegnato testo alternativo, impostato riquadri di delimitazione e apportato modifiche al documento PDF, è possibile utilizzare gli esempi di codice sorgente C# forniti per salvare il documento PDF modificato utilizzando il`Save()` metodo.

#### D: Qual è lo scopo del codice sorgente di esempio fornito nel tutorial?

R: Il codice sorgente di esempio funge da riferimento pratico per l'implementazione del tagging e della manipolazione delle immagini utilizzando Aspose.PDF per .NET. È possibile utilizzare questo codice come punto di partenza e modificarlo in base alle proprie esigenze specifiche.

#### D: Posso applicare queste tecniche ad altri tipi di elementi in un documento PDF, non solo alle immagini?

R: Sì, le tecniche dimostrate in questo tutorial possono essere adattate per funzionare con vari tipi di elementi all'interno di un documento PDF. Puoi applicare principi simili per etichettare e manipolare altri elementi come testo, tabelle e altro.

#### D: Come posso convalidare la conformità PDF/UA del documento PDF modificato?

 R: L'esercitazione fornisce esempi di codice sorgente C# che mostrano come convalidare la conformità PDF/UA del documento PDF modificato utilizzando il`Validate()` metodo e generando un report XML.

#### D: Quali altre funzionalità offre Aspose.PDF per .NET per lavorare con i documenti PDF?

R: Aspose.PDF per .NET offre una vasta gamma di funzionalità per lavorare con documenti PDF, tra cui la manipolazione del testo, l'inserimento di immagini, la creazione di tabelle, la gestione dei campi modulo, le firme digitali, le annotazioni e altro ancora. Consulta la documentazione e le risorse ufficiali per ulteriori esplorazioni.