---
title: Da XML a PDFImposta percorso immagine
linktitle: Da XML a PDFImposta percorso immagine
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata per impostare il percorso di un'immagine durante la conversione da XML a PDF con Aspose.PDF per .NET.
type: docs
weight: 340
url: /it/net/document-conversion/xml-to-pdfset-image-path/
---

In questo tutorial, ti guideremo passo dopo passo su come impostare il percorso di un'immagine durante la conversione di un file XML in PDF utilizzando la libreria Aspose.PDF per .NET. Descriveremo in dettaglio il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti. Alla fine di questo tutorial, puoi facilmente specificare il percorso di un'immagine durante la conversione da XML a PDF.

## Passaggio 1: impostare i percorsi dei file
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 Definire i percorsi dei file XML di input, l'immagine da utilizzare e il file PDF di output. Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso in cui hai salvato i tuoi file.

## Passaggio 2: creare un'istanza di un oggetto Document
```csharp
Document doc = new Document();
```
Creare un'istanza dell'oggetto Document.

## Passaggio 3: collegare il file XML di origine
```csharp
doc. BindXml(inXml);
```
Collega il file XML di origine al documento.

## Passaggio 4: impostare il percorso dell'immagine
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
Ottieni il riferimento all'oggetto Immagine dall'XML usando il suo ID e imposta il percorso dell'immagine da usare.

## Passaggio 5: salvare il file PDF risultante
```csharp
doc.Save(outFile);
```
Salva il file PDF risultante nella directory specificata.

### Codice sorgente di esempio per il percorso dell'immagine da XML a PDFSet utilizzando Aspose.Words per .NET

```csharp
try
{
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare il percorso di un'immagine durante la conversione da XML a PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo i passaggi forniti, puoi facilmente specificare il percorso dell'immagine nelle tue conversioni da XML a PDF.