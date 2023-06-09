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
//Definire il titolo per il documento PDF con tag
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

// Ottiene il contenuto con tag e l'elemento della struttura principale
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

// Controllo della conformità PDF/UA per il nostro documento
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusione

In questo tutorial, abbiamo imparato come contrassegnare un'immagine in un PDF esistente utilizzando Aspose.PDF per .NET. Ora puoi utilizzare Aspose.PDF per aggiungere tag e apportare modifiche alle immagini nei tuoi documenti PDF.
