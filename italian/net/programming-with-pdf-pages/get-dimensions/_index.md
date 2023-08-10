---
title: Ottieni le dimensioni della pagina PDF
linktitle: Ottieni le dimensioni della pagina PDF
second_title: Aspose.PDF per riferimento API .NET
description: In questo tutorial, spieghiamo come ottenere le dimensioni della pagina PDF ed eseguire manipolazioni utilizzando Aspose.PDF per .NET. Vengono forniti passaggi dettagliati per guidare l'utente attraverso il processo.
type: docs
weight: 60
url: /it/net/programming-with-pdf-pages/get-dimensions/
---
In questo tutorial, ti guideremo attraverso il processo passo passo per ottenere le dimensioni della pagina in un file PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come ottenere le dimensioni di una pagina in un file PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza di base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui si trova il tuo file PDF. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il documento PDF
 Quindi è possibile aprire il file PDF utilizzando il file`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto del file PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Passaggio 3: aggiungi una pagina vuota (se necessario)
 Se il documento PDF contiene già delle pagine, puoi passare a una pagina esistente utilizzando il file index`1` (la prima pagina ha un indice di 1). Altrimenti, puoi aggiungere una nuova pagina al documento.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Passaggio 4: ottieni le dimensioni della pagina
 Ora puoi ottenere le dimensioni della pagina utilizzando il file`GetPageRect()` metodo del`Page` oggetto. Questo metodo restituisce a`Rectangle` oggetto contenente le dimensioni della pagina. È possibile accedere alla larghezza e all'altezza utilizzando il file`Width` E`Height` proprietà.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Passaggio 5: ruotare la pagina
 Se vuoi ruotare la pagina, puoi usare il`Rotate` proprietà del`Page`oggetto. In questo esempio, la pagina viene ruotata di 90 gradi.

```csharp
page. Rotate = Rotate. on90;
```

## Passaggio 6: ottieni nuovamente le dimensioni della pagina
 Dopo la rotazione della pagina, puoi ottenere nuovamente le dimensioni della pagina utilizzando il file`GetPageRect()` metodo.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Esempio di codice sorgente per Ottieni dimensioni utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Aggiunge una pagina vuota al documento pdf
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Ottieni informazioni sull'altezza e la larghezza della pagina
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Ruota la pagina con un angolo di 90 gradi
page.Rotate = Rotation.on90;
// Ottieni informazioni sull'altezza e la larghezza della pagina
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Conclusione
In questo tutorial, abbiamo imparato come ottenere le dimensioni di una pagina in un file PDF utilizzando Aspose.PDF per .NET. Seguendo i passaggi forniti, puoi facilmente estrarre le dimensioni della pagina ed eseguire altre operazioni di manipolazione del PDF. Aspose.PDF per .NET offre una grande flessibilità per lavorare con i file PDF e consente di sviluppare soluzioni potenti e personalizzate.

Sentiti libero di esplorare ulteriormente la documentazione di Aspose.PDF per scoprire tutte le funzionalità offerte da questa libreria.

### Domande frequenti per ottenere le dimensioni della pagina PDF

#### D: Come posso ottenere le dimensioni di una pagina specifica in un file PDF?

R: Per ottenere le dimensioni di una pagina specifica in un file PDF, puoi utilizzare il file`GetPageRect()` metodo del`Page` oggetto in Aspose.PDF per .NET. Questo metodo restituisce a`Rectangle` oggetto contenente le dimensioni (larghezza e altezza) della pagina.

####  D: Che cosa significa`GetPageRect(true)` method do in the provided C# source code?

 R: Il`GetPageRect(true)` Il metodo nel codice sorgente C# fornito restituisce le dimensioni della pagina dopo aver applicato eventuali rotazioni. Se la pagina viene ruotata, il metodo restituirà le dimensioni della pagina ruotata, che potrebbero essere diverse dalle dimensioni originali.

#### D: Posso ottenere le dimensioni di tutte le pagine del documento PDF utilizzando Aspose.PDF per .NET?

 R: Sì, puoi ottenere le dimensioni di tutte le pagine nel documento PDF scorrendo il file`Pages` raccolta del`Document` oggetto e utilizzando il`GetPageRect(true)` metodo per ogni pagina.

#### D: Come posso determinare l'orientamento di una pagina (verticale o orizzontale) in base alle sue dimensioni?

R: Per determinare l'orientamento di una pagina in base alle sue dimensioni, puoi confrontare la larghezza e l'altezza della pagina. Se la larghezza è maggiore dell'altezza, la pagina è in orientamento orizzontale e se l'altezza è maggiore della larghezza, la pagina è in orientamento verticale.

#### D: Posso modificare le dimensioni di una pagina utilizzando Aspose.PDF per .NET?

 A: Sì, è possibile modificare le dimensioni di una pagina in Aspose.PDF per .NET. Dopo aver ottenuto il`Rectangle` oggetto che rappresenta le dimensioni della pagina, è possibile regolare la larghezza e l'altezza in base alle proprie esigenze e quindi applicare le modifiche alla pagina.