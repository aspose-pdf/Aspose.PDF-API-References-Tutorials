---
title: Estrai testo dall'area della pagina nel file PDF
linktitle: Estrai testo dall'area della pagina nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre testo da una regione specifica in un PDF usando Aspose.PDF per .NET con questa guida passo-passo. Raccogli e salva in modo efficiente il testo dai tuoi documenti.
type: docs
weight: 190
url: /it/net/programming-with-text/extract-text-from-page-region/
---
## Introduzione

Lavorare con i PDF spesso richiede l'estrazione di contenuti specifici, che si tratti di estrarre dati da moduli, tabelle o determinate sezioni di un documento. In questo tutorial, illustreremo come estrarre testo da una regione specifica di un PDF utilizzando Aspose.PDF per .NET. Invece di setacciare un intero documento, individueremo esattamente dove risiede il testo e lo estrarremo in modo efficiente.

## Prerequisiti

Prima di passare al codice, assicurati di avere a disposizione i seguenti elementi:

1.  Aspose.PDF per .NET: se non l'hai ancora fatto, scarica e installa la libreria Aspose.PDF per .NET.[Scarica Aspose.PDF per .NET](https://releases.aspose.com/pdf/net/).
2. IDE: qualsiasi ambiente di sviluppo .NET come Visual Studio.
3. .NET Framework: assicurati che il tuo progetto sia configurato con il .NET Framework appropriato.
4. Documento PDF: un PDF di esempio da cui estrarremo il testo.

 Non dimenticare che puoi[Ottieni una prova gratuita](https://releases.aspose.com/) di Aspose.PDF o utilizzare un[licenza temporanea](https://purchase.aspose.com/temporary-license/) per la piena funzionalità.

## Importazione dei pacchetti necessari

Per iniziare a lavorare con Aspose.PDF per .NET, devi importare i namespace richiesti nel tuo progetto. Questi pacchetti forniscono le classi e i metodi necessari per gestire i documenti PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Passaggio 1: impostazione della directory dei documenti e caricamento del PDF

Il primo passo è specificare dove si trova il tuo file PDF e caricarlo nel tuo progetto. Puoi usare un percorso di directory locale per il file PDF con cui desideri lavorare.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri il documento PDF
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

 Questo passaggio assicura che il file PDF sia caricato correttamente e pronto per essere elaborato.`Document` La classe della libreria Aspose.PDF consente di manipolare il file PDF.

## Passaggio 2: inizializzare il Text Absorber per l'estrazione

 In questo passaggio creiamo un`TextAbsorber` oggetto, che è progettato per estrarre testo da un documento PDF. L'`TextAbsorber` è flessibile e può essere personalizzato per concentrarsi su regioni o pagine specifiche.

```csharp
// Crea un oggetto TextAbsorber per estrarre il testo
TextAbsorber absorber = new TextAbsorber();
```

 IL`TextAbsorber`class è uno strumento potente che cattura tutto il testo entro i limiti specificati.

## Passaggio 3: definire la regione da cui estrarre il testo

Ecco dove avviene la magia. Invece di estrarre testo dall'intera pagina, possiamo limitare l'estrazione a una specifica regione rettangolare della pagina. Questo è perfetto quando sai esattamente dove si trova il tuo contenuto.

```csharp
// Limita l'estrazione del testo a una regione specifica
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
```

 IL`Rectangle` oggetto consente di definire le coordinate (in punti) dell'area da cui verrà estratto il testo. L'`TextSearchOptions.LimitToPageBounds` assicura che venga estratto solo il testo all'interno del rettangolo specificato.

## Passaggio 4: accettare l'assorbitore sulla pagina desiderata

 Dopo aver impostato la regione, il passo successivo è accettare l'`TextAbsorber` per la pagina specifica da cui vuoi estrarre il testo. Qui, ci concentreremo sulla prima pagina del PDF.

```csharp
// Accetta l'assorbitore per la prima pagina
pdfDocument.Pages[1].Accept(absorber);
```

 Chiamando il`Accept` sulla pagina, istruiamo Aspose.PDF a eseguire l'assorbitore e a raccogliere il testo dalla regione definita.

## Passaggio 5: recuperare e archiviare il testo estratto

 Una volta che l'assorbitore ha svolto il suo lavoro, è il momento di raccogliere il testo estratto e salvarlo. Questo passaggio comporta il recupero del testo e la sua scrittura su un`.txt` file.

```csharp
// Ottieni il testo estratto
string extractedText = absorber.Text;

// Crea uno scrittore per salvare il testo estratto
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");

// Scrivi il testo nel file
tw.WriteLine(extractedText);

// Chiudi il flusso
tw.Close();
```

 Qui, il`TextWriter` class viene utilizzata per scrivere il testo estratto in un file di testo. Ciò garantisce che il contenuto estratto venga archiviato in modo sicuro per un uso successivo.

## Conclusione

 Estrarre testo da una regione specifica all'interno di un documento PDF può essere incredibilmente utile, specialmente quando si ha a che fare con contenuti strutturati come form o tabelle. Utilizzando Aspose.PDF per .NET, è possibile ottenere questo compito con solo poche righe di codice. Definendo una regione, inizializzando un`TextAbsorber`e salvando il testo estratto, avrai il pieno controllo su ciò che verrà estratto dal tuo PDF.

Che tu stia lavorando a un piccolo progetto o gestendo documenti di grandi dimensioni, questo metodo fornisce un modo efficiente per estrarre dati rilevanti dai tuoi PDF senza dover esaminare l'intero documento.

## Domande frequenti

### Posso estrarre il testo da più pagine contemporaneamente?
 Sì, iterando attraverso il`Pages` raccolta di`pdfDocument` , puoi applicare il`TextAbsorber` su più pagine.

### Cosa succede se il testo si trova in un'area diversa del PDF?
 Puoi facilmente regolare il`Rectangle` coordinate corrispondenti alla regione in cui si trova il testo.

### Funziona anche con i PDF scansionati?
No, i PDF scansionati necessitano dell'OCR (riconoscimento ottico dei caratteri) per convertire le immagini in testo. Aspose.PDF offre anche funzionalità OCR.

### Esiste un modo per estrarre il testo in base a parole chiave specifiche?
 Sì, puoi usare`TextFragmentAbsorber` per l'estrazione di testo basata su parole chiave.

### Come faccio a estrarre il testo da un PDF crittografato?
Per prima cosa dovrai decifrare il PDF inserendo la password corretta, per poi procedere con l'estrazione del testo.