---
title: Ottieni la finestra del documento
linktitle: Ottieni la finestra del documento
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare la funzione GetDocumentWindow di Aspose.PDF per .NET per recuperare informazioni sulle proprietà della finestra di un documento PDF.
type: docs
weight: 170
url: /it/net/programming-with-document/getdocumentwindow/
---

 Aspose.PDF per .NET è una potente libreria di manipolazione PDF che consente agli sviluppatori di creare, modificare e convertire file PDF nelle loro applicazioni .NET. Una delle funzionalità offerte da questa libreria è la capacità di recuperare informazioni sulle proprietà della finestra di un documento. Questo tutorial ti guiderà attraverso le fasi di utilizzo del`GetDocumentWindow` caratteristica di Aspose.PDF per. NET per recuperare informazioni sulle proprietà della finestra di un documento PDF.

## Passo 1: Installa Aspose.PDF per .NET

 Per utilizzare Aspose.PDF per .NET nelle tue applicazioni .NET, devi prima installare la libreria. È possibile scaricare l'ultima versione della libreria dal file[Pagina di download di Aspose.PDF per .NET](https://releases.aspose.com/pdf/net).

Una volta scaricata la libreria, estrai il contenuto del file ZIP in una cartella del tuo computer. Sarà quindi necessario aggiungere un riferimento alla DLL Aspose.PDF per .NET nel progetto .NET.

## Passaggio 2: caricare il documento PDF

 Dopo aver installato Aspose.PDF per .NET e aggiunto un riferimento alla DLL nel tuo progetto .NET, puoi iniziare a utilizzare il`GetDocumentWindow` funzione per recuperare informazioni sulle proprietà della finestra di un documento PDF.

Il primo passaggio per utilizzare questa funzione è caricare il documento PDF di cui si desidera recuperare le informazioni. Per fare ciò, puoi utilizzare il seguente codice:

```csharp
// Il percorso del documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Apri il documento PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Nel codice sopra, sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui si trova il documento PDF. Questo codice caricherà il documento PDF in un file`Document` oggetto, che è quindi possibile utilizzare per recuperare informazioni sulle proprietà della finestra del documento.

## Passaggio 3: recuperare le proprietà della finestra del documento

Per recuperare informazioni sulle proprietà della finestra di un documento PDF, è possibile utilizzare il seguente codice:

```csharp
// Recupera le proprietà della finestra del documento
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

Nel codice precedente, ogni riga recupera una diversa proprietà della finestra del documento PDF e la invia alla console. Puoi personalizzare questo codice per recuperare solo le proprietà che ti interessano.

### Codice sorgente di esempio per ottenere la finestra del documento del file PDF utilizzando Aspose.PDF per .NET 

 Ecco il codice sorgente completo per il recupero delle proprietà della finestra di un documento PDF utilizzando il file`GetDocumentWindow` caratteristica di Aspose.PDF per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Ottieni diverse proprietà del documento
// Posizione della finestra del documento - Predefinito: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Ordine di lettura predominante; determina la posizione della pagina
// Se visualizzati fianco a fianco - Predefinito: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Indica se la barra del titolo della finestra deve visualizzare il titolo del documento
// Se falso, la barra del titolo visualizza il nome del file PDF - Predefinito: falso
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Se ridimensionare la finestra del documento per adattarla alle dimensioni di
// Prima pagina visualizzata - Predefinito: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Se nascondere la barra dei menu dell'applicazione visualizzatore - Predefinito: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Se nascondere la barra degli strumenti dell'applicazione visualizzatore - Predefinito: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Se nascondere gli elementi dell'interfaccia utente come le barre di scorrimento
// E lasciando visualizzato solo il contenuto della pagina - Predefinito: falso
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Modalità pagina del documento. Come visualizzare il documento all'uscita dalla modalità a schermo intero.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Il layout della pagina, cioè pagina singola, una colonna
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Come deve essere visualizzato il documento una volta aperto
// Cioè mostra le miniature, a schermo intero, mostra il pannello degli allegati
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```
