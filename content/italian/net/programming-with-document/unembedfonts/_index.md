---
title: Disincorpora i font e ottimizza i file PDF
linktitle: Disincorpora i font e ottimizza i file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre i font e ottimizzare i file PDF utilizzando Aspose.PDF per .NET in questo tutorial passo dopo passo.
type: docs
weight: 370
url: /it/net/programming-with-document/unembedfonts/
---
## Introduzione

Nell'era digitale, i PDF sono onnipresenti. Che tu stia condividendo report, presentazioni o eBook, il Portable Document Format (PDF) è la scelta ideale per mantenere l'integrità dei tuoi documenti. Tuttavia, man mano che creiamo e condividiamo più PDF, le dimensioni dei file possono aumentare, rendendoli difficili da inviare o archiviare. È qui che entra in gioco Aspose.PDF per .NET, offrendo potenti strumenti per ottimizzare i tuoi file PDF. In questo tutorial, approfondiremo come estrarre i font e ottimizzare i file PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti

Prima di entrare nel vivo dell'argomento, assicuriamoci di avere tutto il necessario per iniziare:

1. Visual Studio: assicurati di avere Visual Studio installato sul tuo computer. È l'IDE che useremo per scrivere ed eseguire il nostro codice .NET.
2.  Aspose.PDF per .NET: dovrai scaricare e installare la libreria Aspose.PDF. Puoi prenderla da[collegamento per il download](https://releases.aspose.com/pdf/net/).
3. Conoscenza di base di C#: la familiarità con la programmazione C# ti aiuterà a comprendere i frammenti di codice che utilizzeremo.
4.  Un file PDF: tieni pronto un file PDF che vuoi ottimizzare. Puoi usare qualsiasi PDF, ma per la dimostrazione, lo chiameremo`OptimizeDocument.pdf`.

## Importa pacchetti

Per iniziare, devi importare i pacchetti necessari nel tuo progetto C#. Ecco come puoi farlo:

1. Apri il tuo progetto in Visual Studio.
2. Aggiungere un riferimento ad Aspose.PDF: fare clic con il pulsante destro del mouse sul progetto in Esplora soluzioni, selezionare "Gestisci pacchetti NuGet" e cercare`Aspose.PDF`. Installa il pacchetto.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ora che abbiamo impostato tutto, scomponiamo il processo di ottimizzazione in passaggi gestibili.

## Passaggio 1: imposta la directory dei documenti

Per prima cosa, devi definire il percorso per la directory dei tuoi documenti. È qui che saranno archiviati i tuoi file PDF. Ecco come fare:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui si trova il tuo file PDF. Questo è fondamentale perché il programma deve sapere dove trovare il PDF che vuoi ottimizzare.

## Passaggio 2: aprire il documento PDF

Ora che abbiamo impostato la nostra directory, è il momento di aprire il documento PDF che vogliamo ottimizzare. Ecco il codice per farlo:

```csharp
// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 Questa riga di codice crea un nuovo`Document` object, che rappresenta il tuo file PDF. Assicurati che il nome del file corrisponda a quello che hai nella tua directory.

## Passaggio 3: imposta le opzioni di ottimizzazione

Poi, dobbiamo specificare le opzioni di ottimizzazione. In questo caso, vogliamo rimuovere i font incorporati. Ecco come impostarlo:

```csharp
// Imposta l'opzione UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    UnembedFonts = true
};
```

 Impostando`UnembedFonts` A`true`, stiamo istruendo Aspose.PDF a ottimizzare il PDF estraendo i font. Questo può ridurre significativamente le dimensioni del file, specialmente se il PDF contiene molti font incorporati.

## Passaggio 4: Ottimizza il documento PDF

Con le nostre opzioni impostate, è il momento di ottimizzare il documento PDF. Ecco il codice per farlo:

```csharp
Console.WriteLine("Start");
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

Questo frammento di codice richiama il`OptimizeResources` metodo sul`pdfDocument` oggetto, applicando le opzioni di ottimizzazione che abbiamo definito in precedenza. Vedrai un messaggio nella console che indica che il processo di ottimizzazione è iniziato.

## Passaggio 5: Salvare il documento aggiornato

Dopo aver ottimizzato il PDF, dobbiamo salvare il documento aggiornato. Ecco come fare:

```csharp
// Salva il documento aggiornato
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
```

 Questo codice salva il PDF ottimizzato come`OptimizeDocument_out.pdf` nella stessa directory. Puoi scegliere un nome diverso se preferisci, ma mantenerlo simile aiuta a identificare la versione originale e quella ottimizzata.

## Passaggio 6: confronta le dimensioni dei file

Infine, è sempre bene controllare quanto spazio hai risparmiato. Ecco come confrontare le dimensioni originali e ottimizzate dei file:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Questo codice recupera le dimensioni dei file sia dei PDF originali che di quelli ottimizzati e li stampa sulla console. È un momento soddisfacente vedere quanto hai ridotto le dimensioni del file!

## Conclusione

Ed ecco fatto! Hai rimosso con successo i font e ottimizzato un file PDF usando Aspose.PDF per .NET. Questo processo non solo aiuta a ridurre le dimensioni dei file, ma migliora anche le prestazioni dei tuoi documenti PDF. Che tu stia condividendo file via e-mail o archiviandoli nel cloud, una dimensione di file più piccola può fare un mondo di differenza.

## Domande frequenti

### Che cos'è Aspose.PDF per .NET?
Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, manipolare e ottimizzare i documenti PDF a livello di programmazione.

### Posso usare Aspose.PDF gratuitamente?
 Sì, Aspose offre una versione di prova gratuita. Puoi scaricarla da[Qui](https://releases.aspose.com/).

### Come posso ottenere supporto per Aspose.PDF?
 Puoi ottenere supporto tramite[Forum di Aspose](https://forum.aspose.com/c/pdf/10).

### Quali tipi di ottimizzazioni posso eseguire sui PDF?
Puoi estrarre i font, comprimere le immagini, rimuovere gli oggetti inutilizzati e altro ancora per ottimizzare i tuoi file PDF.

### Dove posso acquistare Aspose.PDF per .NET?
 Puoi acquistare una licenza da[Pagina di acquisto Aspose](https://purchase.aspose.com/buy).