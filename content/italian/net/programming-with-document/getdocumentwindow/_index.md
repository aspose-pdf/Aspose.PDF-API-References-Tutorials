---
title: Ottieni finestra documento
linktitle: Ottieni finestra documento
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come utilizzare la funzionalità GetDocumentWindow di Aspose.PDF per .NET per recuperare informazioni sulle proprietà della finestra di un documento PDF.
type: docs
weight: 170
url: /it/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF per .NET è una potente libreria di manipolazione PDF che consente agli sviluppatori di creare, modificare e convertire file PDF nelle loro applicazioni .NET. Una delle funzionalità offerte da questa libreria è la possibilità di recuperare informazioni sulle proprietà della finestra di un documento. Questo tutorial ti guiderà attraverso i passaggi per utilizzare`GetDocumentWindow` funzionalità di Aspose.PDF per .NET per recuperare informazioni sulle proprietà della finestra di un documento PDF.

## Passaggio 1: installare Aspose.PDF per .NET

 Per utilizzare Aspose.PDF per .NET nelle tue applicazioni .NET, devi prima installare la libreria. Puoi scaricare l'ultima versione della libreria da[Pagina di download di Aspose.PDF per .NET](https://releases.aspose.com/pdf/net).

Una volta scaricata la libreria, estrai il contenuto del file ZIP in una cartella sul tuo computer. Dovrai quindi aggiungere un riferimento alla DLL Aspose.PDF for .NET nel tuo progetto .NET.

## Passaggio 2: caricare il documento PDF

 Dopo aver installato Aspose.PDF per .NET e aggiunto un riferimento alla DLL nel progetto .NET, è possibile iniziare a utilizzare`GetDocumentWindow`funzionalità per recuperare informazioni sulle proprietà della finestra di un documento PDF.

Il primo passo per usare questa funzionalità è caricare il documento PDF di cui vuoi recuperare le informazioni. Per farlo, puoi usare il seguente codice:

```csharp
// Il percorso verso il documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri il documento PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Nel codice sopra, sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso alla directory in cui si trova il tuo documento PDF. Questo codice caricherà il documento PDF in un`Document` oggetto, che puoi quindi utilizzare per recuperare informazioni sulle proprietà della finestra del documento.

## Passaggio 3: recuperare le proprietà della finestra del documento

Per recuperare informazioni sulle proprietà della finestra di un documento PDF, puoi utilizzare il seguente codice:

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

Nel codice sopra, ogni riga recupera una diversa proprietà della finestra del documento PDF e la invia alla console. Puoi personalizzare questo codice per recuperare solo le proprietà che ti interessano.

### Esempio di codice sorgente per ottenere la finestra del documento del file PDF utilizzando Aspose.PDF per .NET 

 Ecco il codice sorgente completo per recuperare le proprietà della finestra di un documento PDF utilizzando`GetDocumentWindow` funzionalità di Aspose.PDF per .NET:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Ottieni diverse proprietà del documento
// Posizione della finestra del documento - Predefinito: falso
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Ordine di lettura predominante; determina la posizione della pagina
// Quando vengono visualizzati affiancati - Predefinito: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Se la barra del titolo della finestra deve visualizzare il titolo del documento
// Se falso, la barra del titolo visualizza il nome del file PDF - Predefinito: falso
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Se ridimensionare la finestra del documento per adattarla alle dimensioni di
// Prima pagina visualizzata - Predefinito: falso
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Se nascondere la barra dei menu dell'applicazione di visualizzazione - Predefinito: falso
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// Se nascondere la barra degli strumenti dell'applicazione di visualizzazione - Predefinito: falso
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Se nascondere gli elementi dell'interfaccia utente come le barre di scorrimento
// E lasciando visualizzato solo il contenuto della pagina - Predefinito: falso
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//Modalità pagina del documento. Come visualizzare il documento all'uscita dalla modalità a schermo intero.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Il layout della pagina, ovvero pagina singola, una colonna
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Come dovrebbe essere visualizzato il documento quando viene aperto
// Mostra miniature, schermo intero, mostra pannello allegati
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Conclusione

In questo tutorial, abbiamo imparato come usare Aspose.PDF per .NET per recuperare informazioni sulle proprietà della finestra di un documento PDF. Caricando un documento PDF e accedendo alle sue proprietà della finestra, puoi raccogliere informazioni su come il documento dovrebbe essere visualizzato quando viene aperto in un'applicazione di visualizzazione. Aspose.PDF per .NET fornisce un potente set di funzionalità per lavorare con file PDF a livello di programmazione, rendendolo uno strumento prezioso per la manipolazione di PDF nelle applicazioni .NET.

### Domande frequenti

#### D: Qual è lo scopo del recupero delle proprietà della finestra di un documento PDF?

R: Recuperare le proprietà della finestra di un documento PDF consente di raccogliere informazioni su come il documento PDF dovrebbe essere visualizzato quando viene aperto in un'applicazione di visualizzazione. Queste proprietà controllano vari aspetti, come la posizione della finestra, la modalità di visualizzazione e la visibilità degli elementi dell'interfaccia utente.

#### D: Come posso installare Aspose.PDF per .NET nel mio progetto .NET?

 A: Per installare Aspose.PDF per .NET, è necessario scaricare la libreria da[Pagina di download di Aspose.PDF per .NET](https://releases.aspose.com/pdf/net)Dopo il download, estrai il contenuto del file ZIP e aggiungi un riferimento alla DLL Aspose.PDF per .NET nel tuo progetto .NET.

#### D: Posso personalizzare il codice per recuperare solo proprietà specifiche della finestra?

R: Sì, puoi personalizzare il codice per recuperare specifiche proprietà della finestra commentando le righe di cui non hai bisogno. Ogni riga nel codice corrisponde a una specifica proprietà della finestra, quindi puoi includere o escludere proprietà in base alle tue esigenze.

#### D: Quali tipi di proprietà delle finestre posso recuperare utilizzando Aspose.PDF per .NET?

R: Utilizzando Aspose.PDF per .NET, è possibile recuperare varie proprietà della finestra di un documento PDF, tra cui la centratura della finestra, l'impostazione del layout di pagina, il controllo della visualizzazione delle barre degli strumenti e delle barre dei menu e altro ancora.