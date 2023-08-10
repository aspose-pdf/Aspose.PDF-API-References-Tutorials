---
title: Ottieni informazioni sul file nel file PDF
linktitle: Ottieni informazioni sul file nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare la funzione GetFileInfo nel file PDF di Aspose.PDF per .NET per recuperare informazioni sui metadati su un documento PDF.
type: docs
weight: 180
url: /it/net/programming-with-document/getfileinfo/
---
Aspose.PDF per .NET è una popolare libreria di manipolazione PDF che consente agli sviluppatori di creare, modificare e convertire file PDF nelle loro applicazioni .NET. Una delle funzionalità offerte da questa libreria è la capacità di recuperare informazioni sui metadati di un documento PDF. Questo tutorial ti guiderà attraverso le fasi di utilizzo del`GetFileInfo` caratteristica di Aspose.PDF per .NET per recuperare informazioni sui metadati di un documento PDF.

## Passo 1: Installa Aspose.PDF per .NET

 Per utilizzare Aspose.PDF per .NET nelle tue applicazioni .NET, devi prima installare la libreria. È possibile scaricare l'ultima versione della libreria dal file[Pagina di download di Aspose.PDF per .NET](https://releases.aspose.com/pdf/net).

Una volta scaricata la libreria, estrai il contenuto del file ZIP in una cartella del tuo computer. Sarà quindi necessario aggiungere un riferimento alla DLL Aspose.PDF per .NET nel progetto .NET.

## Passaggio 2: caricare il documento PDF

 Dopo aver installato Aspose.PDF per .NET e aggiunto un riferimento alla DLL nel tuo progetto .NET, puoi iniziare a utilizzare il`GetFileInfo` funzione per recuperare informazioni sui metadati di un documento PDF.

Il primo passaggio per utilizzare questa funzione è caricare il documento PDF di cui si desidera recuperare le informazioni. Per fare ciò, puoi utilizzare il seguente codice:

```csharp
// Il percorso del documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Apri il documento PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Nel codice sopra, sostituisci`"YOUR DOCUMENT DIRECTORY"`con il percorso della directory in cui si trova il documento PDF. Questo codice caricherà il documento PDF in un file`Document` oggetto, che puoi quindi utilizzare per recuperare informazioni sui metadati del documento.

## Passaggio 3: recuperare i metadati del documento

Per recuperare informazioni sui metadati di un documento PDF, puoi utilizzare il seguente codice:

```csharp
// Ottieni informazioni sul documento
DocumentInfo docInfo = pdfDocument.Info;

// Mostra informazioni sul documento
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

Nel codice precedente, ogni riga recupera una diversa proprietà dei metadati del documento PDF e la invia alla console. Puoi personalizzare questo codice per recuperare solo le proprietà che ti interessano.

### Esempio di codice sorgente per ottenere informazioni sul file PDF utilizzando Aspose.PDF per .NET

 Ecco il codice sorgente completo per il recupero dei metadati di un documento PDF utilizzando il file`GetFileInfo` caratteristica di Aspose.PDF per .NET:

```csharp
// Il percorso del documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Apri il documento PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Ottieni informazioni sul documento
DocumentInfo docInfo = pdfDocument.Info;

// Mostra informazioni sul documento
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Conclusione

In questo tutorial, abbiamo discusso su come utilizzare Aspose.PDF per .NET per recuperare informazioni sui metadati di un documento PDF. Caricando un documento PDF e accedendo alle relative proprietà dei metadati, è possibile raccogliere informazioni sulle caratteristiche e proprietà del documento. Aspose.PDF per .NET fornisce un'API semplice e facile da usare per lavorare con documenti PDF, incluso il recupero di informazioni sui metadati, rendendolo uno strumento prezioso per la manipolazione di PDF nelle applicazioni .NET.

### FAQ

#### D: Cosa sono i metadati in un documento PDF?

R: I metadati in un documento PDF si riferiscono alle informazioni che descrivono le proprietà e le caratteristiche del documento. Queste informazioni in genere includono il titolo del documento, l'autore, l'oggetto, le parole chiave, la data di creazione, la data di modifica e altro.

#### D: Come posso installare Aspose.PDF per .NET nel mio progetto .NET?

 R: Per installare Aspose.PDF per .NET, è necessario scaricare la libreria dal file[Pagina di download di Aspose.PDF per .NET](https://releases.aspose.com/pdf/net)Dopo il download, estrai il contenuto del file ZIP e aggiungi un riferimento a Aspose.PDF per .NET DLL nel tuo progetto .NET.

#### D: Posso personalizzare il codice per recuperare solo proprietà specifiche dei metadati?

R: Sì, puoi personalizzare il codice per recuperare specifiche proprietà dei metadati commentando le righe che non ti servono. Ogni riga del codice corrisponde a una specifica proprietà dei metadati, quindi puoi includere o escludere le proprietà in base alle tue esigenze.

#### D: Quali tipi di proprietà dei metadati posso recuperare utilizzando Aspose.PDF per .NET?

R: Utilizzando Aspose.PDF per .NET, è possibile recuperare varie proprietà dei metadati di un documento PDF, tra cui l'autore, il titolo, l'oggetto, le parole chiave, la data di creazione e la data di modifica.