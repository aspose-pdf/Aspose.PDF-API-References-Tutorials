---
title: Tagga l'immagine nel PDF esistente
linktitle: Tagga l'immagine nel PDF esistente
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come contrassegnare un'immagine in un PDF esistente con Aspose.PDF per .NET. Una guida passo passo per aggiungere tag alle immagini.
type: docs
weight: 210
url: /it/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
In questo tutorial dettagliato, ti guideremo passo dopo passo attraverso il codice sorgente C# fornito per contrassegnare un'immagine in un PDF esistente utilizzando Aspose.PDF per .NET. Segui le istruzioni sottostanti per capire come aggiungere tag a un'immagine in un PDF.

## Fase 1: Impostazione dell'ambiente

Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo per usare Aspose.PDF per .NET. Ciò include l'installazione della libreria Aspose.PDF e la configurazione del tuo progetto per farvi riferimento.

## Passaggio 2: aprire il documento PDF esistente

In questo passaggio apriremo un documento PDF esistente utilizzando Aspose.PDF.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Percorsi dei file di input e output
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Apri il documento
Document document = new Document(inFile);
```

Abbiamo aperto il documento PDF esistente utilizzando Aspose.PDF.

## Passaggio 3: ottenere il contenuto taggato e l'elemento della struttura radice

Ora otterremo il contenuto taggato del documento PDF e l'elemento della struttura radice corrispondente.

```csharp
// Ottieni contenuto taggato ed elemento struttura radice
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Abbiamo ottenuto il contenuto taggato del documento PDF e l'elemento della struttura radice corrispondente.

## Passaggio 4: impostazione del titolo per il documento PDF taggato

Ora impostiamo il titolo per il documento PDF taggato.

```csharp
// Definisci il titolo per il documento PDF taggato
taggedContent.SetTitle("Document with images");
```

Abbiamo impostato il titolo per il documento PDF taggato.

## Passaggio 5: assegnare testi alternativi e riquadro di delimitazione all'immagine

Ora, a ciascun elemento dell'immagine assegneremo un testo alternativo e un riquadro di delimitazione.

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

Abbiamo assegnato un testo alternativo e un riquadro di delimitazione a ciascun elemento immagine nel documento PDF.

## Passaggio 6: Spostamento dell'elemento Span nel paragrafo

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

## Passaggio 7: salvataggio del documento PDF modificato

Ora che abbiamo apportato le modifiche necessarie, salveremo il documento PDF modificato.

```csharp
// Salva il documento PDF
document. Save(outFile);
```

Abbiamo salvato il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per Tag Image In Existing PDF utilizzando Aspose.PDF per .NET 

```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Apri documento
Document document = new Document(inFile);

// Ottiene il contenuto taggato e l'elemento della struttura radice
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Imposta il titolo per il documento PDF taggato
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

// Sposta l'elemento Span nel paragrafo (trova lo span e il paragrafo sbagliati nel primo TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Sposta l'elemento Span nel paragrafo
spanElement.ChangeParentElement(paragraph);

// Salvare il documento
document.Save(outFile);

//Controllo della conformità PDF/UA per il nostro documento
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusione

In questo tutorial, abbiamo imparato come contrassegnare un'immagine in un PDF esistente usando Aspose.PDF per .NET. Ora puoi usare Aspose.PDF per aggiungere tag e apportare modifiche alle immagini nei tuoi documenti PDF.

### Domande frequenti

#### D: Qual è l'obiettivo principale di questo tutorial sull'etichettatura delle immagini in un PDF esistente utilizzando Aspose.PDF per .NET?

R: L'obiettivo principale di questo tutorial è guidarti attraverso il processo di marcatura di un'immagine all'interno di un documento PDF esistente utilizzando Aspose.PDF per .NET. Il tutorial fornisce istruzioni dettagliate ed esempi di codice sorgente C# per aiutarti a capire come assegnare testo alternativo e caselle di delimitazione alle immagini, spostare elementi all'interno del documento e aggiungere tag alle immagini.

#### D: Quali sono i prerequisiti per seguire questo tutorial sull'etichettatura delle immagini in un PDF utilizzando Aspose.PDF per .NET?

R: Prima di iniziare, assicurati di aver impostato il tuo ambiente di sviluppo per usare Aspose.PDF per .NET. Ciò comporta l'installazione della libreria Aspose.PDF e la configurazione del tuo progetto per farvi riferimento.

#### D: Come posso aprire un documento PDF esistente e accedere al suo contenuto taggato utilizzando Aspose.PDF per .NET?

R: Il tutorial fornisce esempi di codice sorgente C# che dimostrano come aprire un documento PDF esistente utilizzando Aspose.PDF per .NET e accedere al suo contenuto taggato per ulteriori manipolazioni.

#### D: Qual è lo scopo dell'assegnazione di testo alternativo e riquadri di delimitazione alle immagini in un documento PDF?

A: Assegnare testo alternativo e riquadri di delimitazione alle immagini migliora l'accessibilità fornendo testo descrittivo per le immagini e definendone il layout e la posizione all'interno del documento. Queste informazioni sono fondamentali per i lettori di schermo e altre tecnologie assistive.

#### D: Come posso impostare il titolo per un documento PDF taggato utilizzando Aspose.PDF per .NET?

R: Il tutorial include esempi di codice sorgente C# che illustrano come impostare il titolo per un documento PDF taggato utilizzando Aspose.PDF per .NET.

#### D: In cosa consiste il processo di spostamento degli elementi all'interno di un documento PDF?

R: Spostare elementi all'interno di un documento PDF implica la modifica dell'elemento padre di un elemento particolare. In questo tutorial, imparerai come spostare un elemento Span in un elemento Paragraph specificato all'interno di una tabella.

#### D: Come posso salvare il documento PDF modificato dopo aver aggiunto tag e apportato modifiche alle immagini?

 A: Dopo aver aggiunto i tag, assegnato il testo alternativo, impostato le caselle di delimitazione e apportato modifiche al documento PDF, puoi utilizzare gli esempi di codice sorgente C# forniti per salvare il documento PDF modificato utilizzando`Save()` metodo.

#### D: Qual è lo scopo del codice sorgente di esempio fornito nel tutorial?

R: Il codice sorgente di esempio serve come riferimento pratico per implementare il tagging e la manipolazione delle immagini usando Aspose.PDF per .NET. Puoi usare questo codice come punto di partenza e modificarlo per adattarlo alle tue esigenze specifiche.

#### D: Posso applicare queste tecniche ad altri tipi di elementi in un documento PDF, non solo alle immagini?

R: Sì, le tecniche illustrate in questo tutorial possono essere adattate per lavorare con vari tipi di elementi all'interno di un documento PDF. Puoi applicare principi simili per taggare e manipolare altri elementi come testo, tabelle e altro.

#### D: Come posso convalidare la conformità PDF/UA del documento PDF modificato?

 A: Il tutorial fornisce esempi di codice sorgente C# che mostrano come convalidare la conformità PDF/UA del documento PDF modificato utilizzando`Validate()` metodo e generazione di un report XML.

#### D: Quali altre funzionalità offre Aspose.PDF per .NET per lavorare con i documenti PDF?

R: Aspose.PDF per .NET offre un'ampia gamma di funzionalità per lavorare con documenti PDF, tra cui manipolazione del testo, inserimento di immagini, creazione di tabelle, gestione dei campi dei moduli, firme digitali, annotazioni e altro ancora. Consulta la documentazione e le risorse ufficiali per ulteriori approfondimenti.