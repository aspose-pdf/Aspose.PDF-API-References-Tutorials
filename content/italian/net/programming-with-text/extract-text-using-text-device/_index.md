---
title: Estrarre il testo utilizzando il dispositivo di testo
linktitle: Estrarre il testo utilizzando il dispositivo di testo
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre il testo da un documento PDF utilizzando il dispositivo di testo in Aspose.PDF per .NET.
type: docs
weight: 210
url: /it/net/programming-with-text/extract-text-using-text-device/
---
## Introduzione

Estrarre testo da un PDF può essere complicato, soprattutto quando si ha a che fare con documenti che hanno vari formati, font incorporati o layout complessi. Ma con Aspose.PDF per .NET, questo processo diventa un gioco da ragazzi! Che tu voglia convertire pagine di un PDF in testo normale per un'analisi più approfondita o semplicemente estrarre sezioni specifiche, Aspose.PDF ti copre. In questo tutorial, spiegheremo passo dopo passo come estrarre testo da un PDF usando la classe TextDevice in Aspose.PDF. Forniremo anche spiegazioni chiare, così potrai applicare gli stessi metodi ai tuoi progetti con facilità.

## Prerequisiti

Prima di passare al codice, assicurati di avere tutto a posto per seguire. Ecco cosa ti servirà:

1.  Aspose.PDF per .NET: Scarica l'ultima versione da[Pagina di download di Aspose.PDF per .NET](https://releases.aspose.com/pdf/net/).
2. Ambiente di sviluppo: Visual Studio o qualsiasi altro ambiente di sviluppo C#.
3. .NET Framework: assicurati che il tuo progetto sia destinato a .NET Framework 4.x o versione successiva.
4. File PDF di input: un file PDF che utilizzerai per l'estrazione del testo. Inseriscilo in una directory sul tuo computer (ci riferiremo a questo come`YOUR DOCUMENT DIRECTORY`).

## Importa pacchetti

Nella parte superiore del codice, dovrai importare gli spazi dei nomi necessari per lavorare con Aspose.PDF:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Passaggio 1: carica il tuo documento PDF

 Prima di estrarre il testo, dobbiamo caricare il documento PDF in memoria. In questo passaggio, aprirai il tuo PDF usando Aspose.PDF`Document` classe. Ciò ti consentirà di accedere a tutte le pagine e ai contenuti all'interno del file.

```csharp
// Definisci il percorso del tuo documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica il documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Qui, stiamo usando`Document pdfDocument = new Document(dataDir + "input.pdf");` per caricare il PDF. Il`dataDir` variabile contiene il percorso della directory del tuo file PDF. Questo ci darà accesso all'intero documento, consentendoci di scorrere le pagine ed estrarre il contenuto.

## Passaggio 2: impostare uno String Builder per l'archiviazione del testo

 Ora che il documento è caricato, abbiamo bisogno di un modo per memorizzare il testo estratto. Per questo, useremo un`StringBuilder` che consente un'efficiente concatenazione di stringhe.

```csharp
// StringBuilder per contenere il testo estratto
StringBuilder builder = new StringBuilder();
```

 Inizializziamo un`StringBuilder`istanza, che raccoglierà il testo estratto da ogni pagina. È un modo più efficiente per gestire stringhe di grandi dimensioni rispetto alla normale concatenazione di stringhe in un ciclo.

## Passaggio 3: scorrere le pagine PDF

 Successivamente, eseguiamo un ciclo su ogni pagina del documento PDF per estrarre il testo. Elaboreremo ogni pagina singolarmente utilizzando il`TextDevice` classe, che è responsabile della conversione del contenuto PDF in formato testo.

```csharp
// Sfoglia tutte le pagine del PDF
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Elaborare ogni pagina per l'estrazione del testo
}
```

Questo ciclo attraversa ogni pagina del PDF (`pdfDocument.Pages` ). Per ogni pagina, estrarremo il testo e lo aggiungeremo al nostro`StringBuilder`.

## Passaggio 4: estrai il testo da ogni pagina

 Ora, impostiamo il processo di estrazione del testo per ogni pagina. Qui, creeremo un`TextDevice` oggetto e utilizzarlo per elaborare le pagine PDF. L'`TextDevice` estrae testo grezzo o formattato in base alle opzioni di estrazione da noi impostate.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Creare un dispositivo di testo per l'estrazione del testo
    TextDevice textDevice = new TextDevice();
    
    // Imposta le opzioni di estrazione del testo sulla modalità "Pure"
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Estrarre il testo dalla pagina corrente e salvarlo nel flusso di memoria
    textDevice.Process(pdfPage, textStream);

    // Convertire il flusso di memoria in testo
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Aggiungere il testo estratto a StringBuilder
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : IL`TextDevice` La classe viene utilizzata per estrarre il testo dal PDF.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Questa opzione estrae il testo grezzo senza conservare alcuna formattazione come font o posizioni. Puoi anche usare`TextFormattingMode.Raw` se hai bisogno di un maggiore controllo sulla formattazione.
- `textDevice.Process(pdfPage, textStream);` : Elabora ogni pagina del PDF e memorizza il testo estratto in un`MemoryStream`.
-  Infine, convertiamo il testo dal`MemoryStream` a una stringa e aggiungerla a`StringBuilder`.

## Passaggio 5: Salva il testo estratto in un file

 Dopo aver elaborato tutte le pagine, il testo viene memorizzato nel`StringBuilder`L'ultimo passaggio consiste nel salvare il testo estratto in un file.

```csharp
// Definire il percorso di output per il file di testo
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Salva il testo estratto in un file
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` : Questo scrive l'intero contenuto del`StringBuilder` in un file di testo.
- Il percorso per il file di output viene impostato aggiungendo un nome file (`"input_Text_Extracted_out.txt"` ) al`dataDir` sentiero.

## Conclusione

Estrarre testo da un PDF usando Aspose.PDF per .NET è un processo semplice ed efficiente. Seguendo i passaggi descritti in questa guida, puoi facilmente aprire documenti PDF, scorrere le pagine ed estrarre testo in un file di testo. Ciò è particolarmente utile per elaborare grandi volumi di dati PDF, eseguire analisi di testo o convertire documenti per ulteriori manipolazioni.

Con Aspose.PDF, non sei limitato all'estrazione di testo: puoi gestire annotazioni, manipolare immagini o persino convertire PDF in altri formati come HTML o Word. La flessibilità e la potenza di questa libreria la rendono uno strumento inestimabile per la gestione di PDF nelle applicazioni .NET.

## Domande frequenti

### Aspose.PDF può estrarre testo da PDF basati su immagini?
No, Aspose.PDF è progettato per estrarre testo da PDF basati su contenuto. Per i PDF basati su immagini, è necessaria la tecnologia OCR.

### Aspose.PDF mantiene la formattazione durante l'estrazione del testo?
Per impostazione predefinita, il testo viene estratto senza formattazione, ma è possibile modificare le opzioni di estrazione se si desidera mantenere una certa formattazione.

### Posso estrarre il testo da un intervallo di pagine specifico?
Sì, puoi modificare il codice per eseguire un ciclo su un intervallo specifico di pagine anziché su tutte le pagine.

### Quali sono le modalità di estrazione del testo in Aspose.PDF?
Aspose.PDF fornisce due modalità: Raw e Pure. La modalità Raw cerca di mantenere il layout originale, mentre la modalità Pure estrae solo il testo senza formattazione.

### Aspose.PDF per .NET è compatibile con .NET Core?
Sì, Aspose.PDF per .NET è completamente compatibile con .NET Core e .NET Framework.