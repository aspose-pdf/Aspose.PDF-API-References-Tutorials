---
title: Ottieni le dimensioni della pagina PDF
linktitle: Ottieni le dimensioni della pagina PDF
second_title: Riferimento API Aspose.PDF per .NET
description: In questo tutorial, spieghiamo come ottenere le dimensioni della pagina PDF ed eseguire manipolazioni usando Aspose.PDF per .NET. Sono forniti passaggi dettagliati per guidarti attraverso il processo.
type: docs
weight: 60
url: /it/net/programming-with-pdf-pages/get-dimensions/
---
In questo tutorial, ti guideremo passo dopo passo nel processo di ottenimento delle dimensioni di pagina in un file PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come ottenere le dimensioni di una pagina in un file PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Una conoscenza di base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Per prima cosa, devi impostare il percorso per la directory dei tuoi documenti. Questa è la posizione in cui si trova il tuo file PDF. Sostituisci "YOUR DOCUMENTS DIRECTORY" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: aprire il documento PDF
 Quindi puoi aprire il file PDF utilizzando`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto per il file PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Passaggio 3: aggiungere una pagina vuota (se necessario)
 Se il documento PDF contiene già delle pagine, puoi passare a una pagina esistente utilizzando l'indice`1` (la prima pagina ha un indice di 1). Altrimenti, puoi aggiungere una nuova pagina al documento.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Passaggio 4: ottenere le dimensioni della pagina
 Ora puoi ottenere le dimensioni della pagina utilizzando`GetPageRect()` metodo del`Page` oggetto. Questo metodo restituisce un`Rectangle` oggetto contenente le dimensioni della pagina. Puoi accedere alla larghezza e all'altezza utilizzando`Width` E`Height` proprietà.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Passaggio 5: ruota la pagina
 Se vuoi ruotare la pagina puoi usare il`Rotate` proprietà del`Page`oggetto. In questo esempio, la pagina è ruotata di 90 gradi.

```csharp
page. Rotate = Rotate. on90;
```

## Passaggio 6: Ottieni nuovamente le dimensioni della pagina
 Dopo la rotazione della pagina, è possibile ottenere nuovamente le dimensioni della pagina utilizzando`GetPageRect()` metodo.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Esempio di codice sorgente per Get Dimensions utilizzando Aspose.PDF per .NET 

```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Aggiunge una pagina vuota al documento PDF
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Ottieni informazioni su altezza e larghezza della pagina
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Ruota la pagina di 90 gradi
page.Rotate = Rotation.on90;
// Ottieni informazioni su altezza e larghezza della pagina
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Conclusione
In questo tutorial, abbiamo imparato come ottenere le dimensioni di una pagina in un file PDF usando Aspose.PDF per .NET. Seguendo i passaggi forniti, puoi facilmente estrarre le dimensioni della pagina ed eseguire altre operazioni di manipolazione PDF. Aspose.PDF per .NET offre grande flessibilità per lavorare con i file PDF e ti consente di sviluppare soluzioni potenti e personalizzate.

Sentitevi liberi di esplorare ulteriormente la documentazione di Aspose.PDF per scoprire tutte le funzionalità offerte da questa libreria.

### Domande frequenti per ottenere le dimensioni della pagina PDF

#### D: Come posso conoscere le dimensioni di una pagina specifica in un file PDF?

A: Per ottenere le dimensioni di una pagina specifica in un file PDF, puoi utilizzare`GetPageRect()` metodo del`Page` oggetto in Aspose.PDF per .NET. Questo metodo restituisce un`Rectangle` oggetto contenente le dimensioni (larghezza e altezza) della pagina.

####  D: Cosa significa?`GetPageRect(true)` method do in the provided C# source code?

 A: Il`GetPageRect(true)` nel codice sorgente C# fornito restituisce le dimensioni della pagina dopo aver applicato eventuali rotazioni. Se la pagina viene ruotata, il metodo restituirà le dimensioni della pagina ruotata, che potrebbero essere diverse dalle dimensioni originali.

#### D: Posso ottenere le dimensioni di tutte le pagine del documento PDF utilizzando Aspose.PDF per .NET?

 A: Sì, puoi ottenere le dimensioni di tutte le pagine nel documento PDF iterando attraverso il`Pages` raccolta di`Document` oggetto e utilizzando il`GetPageRect(true)` metodo per ogni pagina.

#### D: Come posso determinare l'orientamento di una pagina (verticale o orizzontale) in base alle sue dimensioni?

R: Per determinare l'orientamento di una pagina in base alle sue dimensioni, puoi confrontare la larghezza e l'altezza della pagina. Se la larghezza è maggiore dell'altezza, la pagina è in orientamento orizzontale, e se l'altezza è maggiore della larghezza, la pagina è in orientamento verticale.

#### D: Posso modificare le dimensioni di una pagina utilizzando Aspose.PDF per .NET?

 A: Sì, puoi modificare le dimensioni di una pagina in Aspose.PDF per .NET. Dopo aver ottenuto il`Rectangle` Oggetto che rappresenta le dimensioni della pagina. Puoi regolare la larghezza e l'altezza in base alle tue esigenze e poi applicare le modifiche alla pagina.