---
title: Imposta il nome del font predefinito
linktitle: Imposta il nome del font predefinito
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come impostare un nome font predefinito quando esegui il rendering di PDF in immagini usando Aspose.PDF per .NET. Questa guida copre i prerequisiti, le istruzioni dettagliate e le FAQ.
type: docs
weight: 270
url: /it/net/document-conversion/set-default-font-name/
---
## Introduzione

Hai mai provato a rendere un documento PDF un'immagine ma hai scoperto che i font non sono giusti? Forse il testo appare distorto o forse il font originale non è supportato. Ecco perché impostare un font predefinito può salvare la giornata! Utilizzando Aspose.PDF per .NET, puoi facilmente impostare un font predefinito per il rendering del tuo PDF, assicurandoti che il tuo documento appaia nitido e professionale. In questo tutorial, ti guideremo attraverso come impostare il nome del font predefinito quando si rende un PDF un'immagine. Alla fine di questa guida, avrai le competenze per affrontare qualsiasi sfida di rendering PDF che ti si presenterà. Pronto? Tuffiamoci!

## Prerequisiti

Prima di passare al codice, ecco alcune cose che devi sapere:

- Aspose.PDF per .NET: Questa potente libreria è quella che useremo per manipolare il nostro documento PDF. Puoi scaricarla da[Sito web di Aspose](https://releases.aspose.com/pdf/net/).
- Visual Studio: assicurati di avere Visual Studio installato sul tuo computer. Questo sarà il nostro ambiente di sviluppo.
- .NET Framework: assicurati di avere installato .NET Framework. Aspose.PDF per .NET supporta varie versioni, quindi controlla la documentazione per adattarla alle tue esigenze.
- Un documento PDF: avrai bisogno di un documento PDF di esempio con cui lavorare. Se non ne hai uno, crea un PDF semplice o scarica un esempio online.

Una volta impostato tutto, siamo pronti per iniziare a programmare!

## Importa pacchetti

Prima di immergerci nel codice, è essenziale importare i pacchetti necessari. Questo ci assicura di avere accesso a tutte le classi e i metodi di cui abbiamo bisogno per il nostro progetto.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Queste importazioni sono fondamentali perché introducono gli spazi dei nomi necessari per gestire la manipolazione dei PDF, il rendering delle immagini e le operazioni di flusso dei file.

## Passaggio 1: imposta il percorso del progetto e del documento

Per prima cosa, impostiamo il percorso della directory in cui si trova il tuo documento PDF. Questo sarà il tuo punto di partenza per manipolare il file PDF.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Qui,`dataDir` è la directory in cui risiede il tuo documento PDF. Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo del tuo documento. Questo è essenziale perché il codice deve sapere da dove recuperare il file PDF.

## Passaggio 2: caricare il documento PDF

Ora che abbiamo il percorso del documento, il passo successivo è caricare il documento PDF nella memoria, così da poter iniziare a lavorarci.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 Noi utilizziamo il`Document` classe dalla libreria Aspose.PDF per caricare il nostro file PDF. Questa classe fornisce vari metodi e proprietà per lavorare con il documento PDF. La`"input.pdf"` dovrebbe essere sostituito con il nome effettivo del file del tuo PDF. Questo file verrà utilizzato come input per il rendering.

## Passaggio 3: creare un flusso di immagini per l'output

Una volta caricato il documento, dobbiamo impostare uno stream per salvare l'immagine renderizzata. È qui che verrà salvata l'immagine di output.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 IL`FileStream`la classe viene usata per creare un nuovo file in cui verrà salvata l'immagine renderizzata. In questo esempio, stiamo salvando l'immagine come`"SetDefaultFontName.png"` . IL`FileMode.Create` assicura che venga creato un nuovo file o che un file esistente venga sovrascritto.

## Passaggio 4: imposta la risoluzione per l'immagine

Prima di rendere il PDF un'immagine, è fondamentale impostare la risoluzione. Ciò determina la qualità e la nitidezza dell'immagine di output.

```csharp
Resolution resolution = new Resolution(300);
```
 IL`Resolution` class imposta la risoluzione dell'immagine di output. Qui, abbiamo scelto una risoluzione di 300 DPI (punti per pollice), che è lo standard per le immagini di alta qualità. Ciò assicura che il testo e la grafica nel PDF vengano renderizzati in modo chiaro senza perdere dettagli.

## Passaggio 5: configurare il dispositivo PNG

Ora dobbiamo configurare il dispositivo che gestirà il rendering del PDF in un'immagine PNG.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 IL`PngDevice` la classe è responsabile del rendering del documento PDF in un'immagine PNG. Passando il`resolution` ad esso, ci assicuriamo che l'immagine venga creata con i DPI specificati.

## Passaggio 6: imposta il nome del font predefinito

Ecco la parte critica: impostare il nome del font predefinito. Questo sarà il font di fallback nel caso in cui il font originale nel PDF non sia disponibile.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 Creiamo un'istanza di`RenderingOptions` e imposta il suo`DefaultFontName` proprietà a`"Arial"`. Ciò significa che se il font originale nel PDF non può essere trovato, verrà utilizzato Arial. Questo passaggio è fondamentale per mantenere la leggibilità e l'aspetto del testo nell'immagine renderizzata.

## Passaggio 7: Trasforma la pagina PDF in un'immagine

Infine, una volta impostato tutto, possiamo trasformare la prima pagina del documento PDF in un'immagine e salvarla utilizzando il flusso di file creato in precedenza.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 IL`Process` metodo del`PngDevice` la classe viene utilizzata per rendere la pagina PDF specificata (in questo caso, la prima pagina) in un'immagine. L'output viene quindi salvato nel`imageStream`Questo passaggio converte la pagina PDF in un'immagine PNG con la risoluzione specificata e il font predefinito.

## Passaggio 8: chiudere il flusso di file e il documento PDF

Dopo aver renderizzato l'immagine, è essenziale chiudere il flusso di file e il documento PDF per liberare risorse.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
Chiusura del`imageStream` assicura che il file venga salvato correttamente e che nessun dato venga perso. Smaltimento del`pdfDocument` libera memoria e risorse, prevenendo potenziali perdite di memoria.

## Conclusione

Ed ecco fatto! Con solo poche righe di codice, hai imparato come impostare un nome di font predefinito quando esegui il rendering di un PDF in un'immagine usando Aspose.PDF per .NET. Questa abilità è incredibilmente utile, specialmente quando si ha a che fare con PDF che potrebbero contenere font non supportati. Impostando un font predefinito, ti assicuri che le tue immagini renderizzate mantengano la loro leggibilità e il loro aspetto professionale.

## Domande frequenti

### Cosa succede se il font predefinito specificato non è installato sul sistema?
 Se il font predefinito specificato in`RenderingOptions` non è installato nel sistema, Aspose.PDF utilizzerà un font di fallback definito dal sistema.

### Posso usare font diversi da Arial come font predefinito?
Assolutamente! Puoi impostare qualsiasi font installato sul tuo sistema come font predefinito.

### È possibile convertire più pagine di un PDF in immagini in una sola volta?
Sì, puoi scorrere le pagine del tuo PDF e renderizzare ogni pagina singolarmente utilizzando lo stesso procedimento.

### L'impostazione di una risoluzione elevata influisce sulle prestazioni del rendering PDF?
Sì, risoluzioni più elevate produrranno file immagine più grandi e potrebbero aumentare i tempi di rendering, ma produrranno anche immagini più nitide.

### Posso convertire il PDF in altri formati immagine oltre a PNG?
Sì, Aspose.PDF supporta il rendering in vari formati immagine, quali JPEG, BMP e TIFF.