---
title: Ottieni informazioni sul file in formato PDF
linktitle: Ottieni informazioni sul file in formato PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come utilizzare la funzionalità GetFileInfo nei file PDF di Aspose.PDF per .NET per recuperare informazioni sui metadati di un documento PDF.
type: docs
weight: 180
url: /it/net/programming-with-document/getfileinfo/
---
 Aspose.PDF per .NET è una popolare libreria di manipolazione PDF che consente agli sviluppatori di creare, modificare e convertire file PDF nelle loro applicazioni .NET. Una delle funzionalità offerte da questa libreria è la possibilità di recuperare informazioni sui metadati di un documento PDF. Questo tutorial ti guiderà attraverso i passaggi per utilizzare`GetFileInfo` funzionalità di Aspose.PDF per .NET per recuperare informazioni sui metadati di un documento PDF.

## Passaggio 1: installare Aspose.PDF per .NET

 Per utilizzare Aspose.PDF per .NET nelle tue applicazioni .NET, devi prima installare la libreria. Puoi scaricare l'ultima versione della libreria da[Pagina di download di Aspose.PDF per .NET](https://releases.aspose.com/pdf/net).

Una volta scaricata la libreria, estrai il contenuto del file ZIP in una cartella sul tuo computer. Dovrai quindi aggiungere un riferimento alla DLL Aspose.PDF for .NET nel tuo progetto .NET.

## Passaggio 2: caricare il documento PDF

 Dopo aver installato Aspose.PDF per .NET e aggiunto un riferimento alla DLL nel progetto .NET, è possibile iniziare a utilizzare`GetFileInfo` Funzione per recuperare informazioni sui metadati di un documento PDF.

Il primo passo per usare questa funzionalità è caricare il documento PDF di cui vuoi recuperare le informazioni. Per farlo, puoi usare il seguente codice:

```csharp
// Il percorso verso il documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri il documento PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Nel codice sopra, sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso alla directory in cui si trova il tuo documento PDF. Questo codice caricherà il documento PDF in un`Document` oggetto, che puoi quindi utilizzare per recuperare informazioni sui metadati del documento.

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

Nel codice sopra, ogni riga recupera una diversa proprietà di metadati del documento PDF e la invia alla console. Puoi personalizzare questo codice per recuperare solo le proprietà che ti interessano.

### Esempio di codice sorgente per ottenere informazioni sul file PDF utilizzando Aspose.PDF per .NET

 Ecco il codice sorgente completo per recuperare i metadati di un documento PDF utilizzando`GetFileInfo` funzionalità di Aspose.PDF per .NET:

```csharp
// Il percorso verso il documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri il documento PDF
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

In questo tutorial, abbiamo discusso su come usare Aspose.PDF per .NET per recuperare informazioni sui metadati di un documento PDF. Caricando un documento PDF e accedendo alle sue proprietà dei metadati, puoi raccogliere informazioni sulle caratteristiche e le proprietà del documento. Aspose.PDF per .NET fornisce un'API semplice e facile da usare per lavorare con i documenti PDF, incluso il recupero delle informazioni sui metadati, rendendolo uno strumento prezioso per la manipolazione dei PDF nelle applicazioni .NET.

### Domande frequenti

#### D: Cosa sono i metadati in un documento PDF?

R: I metadati in un documento PDF si riferiscono alle informazioni che descrivono le proprietà e le caratteristiche del documento. Queste informazioni includono in genere il titolo del documento, l'autore, l'oggetto, le parole chiave, la data di creazione, la data di modifica e altro ancora.

#### D: Come posso installare Aspose.PDF per .NET nel mio progetto .NET?

 A: Per installare Aspose.PDF per .NET, è necessario scaricare la libreria da[Pagina di download di Aspose.PDF per .NET](https://releases.aspose.com/pdf/net)Dopo il download, estrai il contenuto del file ZIP e aggiungi un riferimento alla DLL Aspose.PDF per .NET nel tuo progetto .NET.

#### D: Posso personalizzare il codice per recuperare solo proprietà specifiche dei metadati?

R: Sì, puoi personalizzare il codice per recuperare specifiche proprietà dei metadati commentando le righe di cui non hai bisogno. Ogni riga del codice corrisponde a una specifica proprietà dei metadati, quindi puoi includere o escludere proprietà in base alle tue esigenze.

#### D: Quali tipi di proprietà dei metadati posso recuperare utilizzando Aspose.PDF per .NET?

R: Utilizzando Aspose.PDF per .NET, è possibile recuperare varie proprietà dei metadati di un documento PDF, tra cui autore, titolo, oggetto, parole chiave, data di creazione e data di modifica.