---
title: XPS in PDF
linktitle: XPS in PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per convertire file XPS in PDF con Aspose.PDF per .NET.
type: docs
weight: 350
url: /it/net/document-conversion/xps-to-pdf/
---
In questo tutorial, ti spiegheremo come convertire file XPS in PDF utilizzando la libreria Aspose.PDF per .NET passo dopo passo. Descriveremo in dettaglio il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti. Alla fine di questo tutorial sarai in grado di convertire facilmente i file XPS in documenti PDF.

## Passaggio 1: imposta la directory dei documenti
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso in cui hai salvato i tuoi file.

## Passaggio 2: creare un'istanza dell'oggetto LoadOptions utilizzando le opzioni di caricamento XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Crea un'istanza dell'oggetto LoadOptions utilizzando le opzioni di caricamento XPS.

## Passaggio 3: creare l'oggetto documento
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Crea un oggetto Document specificando il file XPS di input e le opzioni di caricamento.

## Passaggio 4: salva il documento PDF risultante
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Salva il documento PDF risultante nella directory specificata.

### Codice sorgente di esempio per XPS in PDF utilizzando Aspose.PDF per .NET

```csharp
try
{
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Crea un'istanza dell'oggetto LoadOption utilizzando l'opzione di caricamento XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Crea oggetto documento
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Salvare il documento PDF risultante
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione
In questo tutorial, abbiamo imparato come convertire file XPS in PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo i passaggi forniti, puoi facilmente eseguire questa conversione nelle tue applicazioni. Ottieni risultati accurati e professionali durante la conversione di file XPS in PDF.

### Domande frequenti

#### D: Cos'è XPS e perché dovrei convertirlo in PDF?

R: XPS (XML Paper Specifica) è un formato di documento a layout fisso sviluppato da Microsoft. La conversione di XPS in PDF ti consente di rendere il documento più accessibile e ampiamente compatibile, poiché il PDF è un formato universalmente supportato su diverse piattaforme e dispositivi.

#### D: La libreria Aspose.PDF supporta altri formati di file oltre a XPS?

R: Sì, Aspose.PDF per .NET supporta vari altri formati di file per la conversione, come HTML, EPUB, SVG, XML e altri. Consente inoltre di creare e manipolare documenti PDF a livello di codice.

#### D: Posso personalizzare il processo di conversione del PDF, ad esempio impostando le dimensioni della pagina, i margini o altre opzioni?

R: Sì, puoi personalizzare il processo di conversione PDF utilizzando Aspose.PDF per .NET. La libreria offre un'ampia gamma di opzioni per controllare le dimensioni della pagina, i margini, la compressione delle immagini, l'incorporamento dei caratteri e altre impostazioni relative ai PDF per soddisfare i tuoi requisiti specifici.

#### D: È disponibile una versione di prova di Aspose.PDF per .NET per il test?

R: Sì, puoi scaricare e provare la versione di prova di Aspose.PDF per .NET dal sito Web ufficiale di Aspose. La versione di prova ti consente di esplorare le funzionalità della libreria prima di effettuare un acquisto.

#### D: Posso convertire più file XPS in PDF in un processo batch?

R: Sì, puoi convertire più file XPS in PDF in un processo batch implementando un ciclo o scorrendo l'elenco dei file XPS e convertendo ciascun file in PDF utilizzando il codice fornito.