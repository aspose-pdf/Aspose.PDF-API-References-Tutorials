---
title: Da XPS a PDF
linktitle: Da XPS a PDF
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire file XPS in PDF con Aspose.PDF per .NET.
type: docs
weight: 350
url: /it/net/document-conversion/xps-to-pdf/
---
In questo tutorial, ti guideremo attraverso come convertire il file XPS in PDF usando la libreria Aspose.PDF per .NET passo dopo passo. Descriveremo in dettaglio il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti. Alla fine di questo tutorial, sarai in grado di convertire facilmente i file XPS in documenti PDF.

## Passaggio 1: imposta la directory dei documenti
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso in cui hai salvato i tuoi file.

## Passaggio 2: creare un'istanza dell'oggetto LoadOptions utilizzando le opzioni di caricamento XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Creare un'istanza dell'oggetto LoadOptions utilizzando le opzioni di caricamento XPS.

## Passaggio 3: creare l'oggetto documento
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Creare un oggetto Document specificando il file XPS di input e le opzioni di caricamento.

## Passaggio 4: salvare il documento PDF risultante
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Salva il documento PDF risultante nella directory specificata.

### Esempio di codice sorgente per XPS in PDF utilizzando Aspose.PDF per .NET

```csharp
try
{
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Crea un'istanza dell'oggetto LoadOption utilizzando l'opzione di caricamento XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Crea oggetto documento
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Salva il documento PDF risultante
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione
In questo tutorial, abbiamo imparato come convertire i file XPS in PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo i passaggi forniti, puoi eseguire facilmente questa conversione nelle tue applicazioni. Ottieni risultati accurati e professionali durante la conversione di file XPS in PDF.

### FAQ

#### D: Cos'è XPS e perché dovrei convertirlo in PDF?

R: XPS (XML Paper Specification) è un formato di documento a layout fisso sviluppato da Microsoft. La conversione di XPS in PDF consente di rendere il documento più accessibile e ampiamente compatibile, poiché il PDF è un formato universalmente supportato su diverse piattaforme e dispositivi.

#### D: La libreria Aspose.PDF supporta altri formati di file oltre a XPS?

A: Sì, Aspose.PDF per .NET supporta vari altri formati di file per la conversione, come HTML, EPUB, SVG, XML e altro. Consente inoltre di creare e manipolare documenti PDF in modo programmatico.

#### D: Posso personalizzare il processo di conversione PDF, ad esempio impostando le dimensioni della pagina, i margini o altre opzioni?

R: Sì, puoi personalizzare il processo di conversione PDF utilizzando Aspose.PDF per .NET. La libreria offre un'ampia gamma di opzioni per controllare le dimensioni della pagina, i margini, la compressione delle immagini, l'incorporamento dei caratteri e altre impostazioni relative ai PDF per soddisfare i requisiti specifici.

#### D: Esiste una versione di prova di Aspose.PDF per .NET disponibile per il test?

R: Sì, puoi scaricare e provare la versione di prova di Aspose.PDF per .NET dal sito web ufficiale di Aspose. La versione di prova ti consente di esplorare le funzionalità della libreria prima di effettuare un acquisto.

#### D: Posso convertire più file XPS in PDF in un processo batch?

R: Sì, puoi convertire più file XPS in PDF in un processo batch implementando un ciclo o iterando l'elenco dei file XPS e convertendo ogni file in PDF utilizzando il codice fornito.