---
title: Ottieni la finestra del documento
linktitle: Ottieni la finestra del documento
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come utilizzare la funzionalità GetDocumentWindow di Aspose.PDF per .NET per recuperare informazioni sulle proprietà della finestra di un documento PDF.
type: docs
weight: 170
url: /it/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF per .NET è una potente libreria di manipolazione PDF che consente agli sviluppatori di creare, modificare e convertire file PDF nelle loro applicazioni .NET. Una delle funzionalità offerte da questa libreria è la capacità di recuperare informazioni sulle proprietà della finestra di un documento. Questo tutorial ti guiderà attraverso i passaggi di utilizzo di`GetDocumentWindow` funzionalità di Aspose.PDF per .NET per recuperare informazioni sulle proprietà della finestra di un documento PDF.

## Passaggio 1: installare Aspose.PDF per .NET

 Per utilizzare Aspose.PDF per .NET nelle tue applicazioni .NET, devi prima installare la libreria. È possibile scaricare l'ultima versione della libreria da[Aspose.PDF per la pagina di download di .NET](https://releases.aspose.com/pdf/net).

Una volta scaricata la libreria, estrai il contenuto del file ZIP in una cartella del tuo computer. Sarà quindi necessario aggiungere un riferimento alla DLL Aspose.PDF per .NET nel progetto .NET.

## Passaggio 2: carica il documento PDF

Dopo aver installato Aspose.PDF per .NET e aggiunto un riferimento alla DLL nel tuo progetto .NET, puoi iniziare a utilizzare il`GetDocumentWindow` funzione per recuperare informazioni sulle proprietà della finestra di un documento PDF.

Il primo passo per utilizzare questa funzionalità è caricare il documento PDF di cui desideri recuperare informazioni. Per fare ciò, puoi utilizzare il seguente codice:

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

### Esempio di codice sorgente per ottenere la finestra del documento del file PDF utilizzando Aspose.PDF per .NET 

 Ecco il codice sorgente completo per recuperare le proprietà della finestra di un documento PDF utilizzando il file`GetDocumentWindow` funzionalità di Aspose.PDF per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Ottieni diverse proprietà del documento
// Posizione della finestra del documento - Predefinita: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Ordine di lettura predominante; determina la posizione della pagina
// Se visualizzati affiancati - Impostazione predefinita: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Indica se la barra del titolo della finestra deve visualizzare il titolo del documento
// Se false, la barra del titolo visualizza il nome del file PDF - Impostazione predefinita: false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Indica se ridimensionare la finestra del documento per adattarla alle dimensioni di
// Prima pagina visualizzata - Predefinito: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Se nascondere la barra dei menu dell'applicazione visualizzatore - Impostazione predefinita: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Se nascondere la barra degli strumenti dell'applicazione visualizzatore - Impostazione predefinita: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Indica se nascondere gli elementi dell'interfaccia utente come le barre di scorrimento
// E lasciando visualizzato solo il contenuto della pagina - Predefinito: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Modalità pagina del documento. Come visualizzare il documento all'uscita dalla modalità a schermo intero.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Il layout della pagina, ovvero una pagina singola, una colonna
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Come dovrebbe essere visualizzato il documento una volta aperto
// Ad esempio, mostra miniature, schermo intero, mostra pannello allegati
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Conclusione

In questo tutorial, abbiamo imparato come utilizzare Aspose.PDF per .NET per recuperare informazioni sulle proprietà della finestra di un documento PDF. Caricando un documento PDF e accedendo alle relative proprietà della finestra, è possibile raccogliere informazioni su come il documento dovrebbe essere visualizzato quando viene aperto in un'applicazione di visualizzazione. Aspose.PDF per .NET fornisce un potente set di funzionalità per lavorare con i file PDF a livello di codice, rendendolo uno strumento prezioso per la manipolazione dei PDF nelle applicazioni .NET.

### Domande frequenti

#### D: Qual è lo scopo del recupero delle proprietà della finestra di un documento PDF?

R: Il recupero delle proprietà della finestra di un documento PDF consente di raccogliere informazioni su come il documento PDF dovrebbe essere visualizzato quando viene aperto in un'applicazione di visualizzazione. Queste proprietà controllano vari aspetti come la posizione della finestra, la modalità di visualizzazione e la visibilità degli elementi dell'interfaccia utente.

#### D: Come posso installare Aspose.PDF per .NET nel mio progetto .NET?

 R: Per installare Aspose.PDF per .NET, è necessario scaricare la libreria da[Aspose.PDF per la pagina di download di .NET](https://releases.aspose.com/pdf/net). Dopo il download, estrai il contenuto del file ZIP e aggiungi un riferimento alla DLL Aspose.PDF per .NET nel tuo progetto .NET.

#### D: Posso personalizzare il codice per recuperare solo proprietà specifiche della finestra?

R: Sì, puoi personalizzare il codice per recuperare proprietà specifiche della finestra commentando le righe che non ti servono. Ogni riga nel codice corrisponde a una proprietà specifica della finestra, quindi puoi includere o escludere proprietà in base alle tue esigenze.

#### D: Quali tipi di proprietà della finestra posso recuperare utilizzando Aspose.PDF per .NET?

R: Utilizzando Aspose.PDF per .NET, puoi recuperare varie proprietà della finestra di un documento PDF, tra cui centrare la finestra, impostare il layout della pagina, controllare la visualizzazione delle barre degli strumenti e delle barre dei menu e altro ancora.