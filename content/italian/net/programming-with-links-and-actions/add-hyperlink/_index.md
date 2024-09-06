---
title: Aggiungi collegamento ipertestuale nel file PDF
linktitle: Aggiungi collegamento ipertestuale nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Aggiungi facilmente collegamenti ipertestuali interattivi nei file PDF con Aspose.PDF per .NET.
type: docs
weight: 10
url: /it/net/programming-with-links-and-actions/add-hyperlink/
---
L'aggiunta di collegamenti ipertestuali nel file PDF consente di creare collegamenti ipertestuali interattivi ad altre pagine, siti Web o destinazioni nel documento. Con Aspose.PDF per .NET, è possibile aggiungere facilmente collegamenti ipertestuali seguendo il seguente codice sorgente:

## Passaggio 1: importare le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## Passaggio 2: imposta il percorso per la cartella dei documenti

 In questo passaggio, devi specificare il percorso della cartella contenente il file PDF a cui vuoi aggiungere un collegamento ipertestuale. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel codice seguente con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: aprire il documento PDF

Ora apriremo il documento PDF al quale vogliamo aggiungere un collegamento ipertestuale utilizzando il seguente codice:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## Passaggio 4: creare un collegamento

 In questo passaggio creeremo un collegamento ipertestuale utilizzando il`LinkAnnotation` annotazione. Specifichiamo i dettagli di contatto e l'area del collegamento, il tipo di collegamento e il contenuto del collegamento. Ecco il codice corrispondente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## Passaggio 5: aggiungere testo aggiuntivo

 Oltre all'hyperlink, possiamo anche aggiungere del testo aggiuntivo utilizzando il`FreeTextAnnotation` annotazione. Specifichiamo coordinate, aspetto del testo e contenuto del testo. Ecco il codice corrispondente:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## Passaggio 6: salvare il file aggiornato

Ora salviamo il file PDF aggiornato utilizzando il`Save` metodo del`document` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### Esempio di codice sorgente per Aggiungi collegamento ipertestuale utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document(dataDir + "AddHyperlink.pdf");
// Crea collegamento
Page page = document.Pages[1];
// Crea oggetto di annotazione del collegamento
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// Crea oggetto bordo per LinkAnnotation
Border border = new Border(link);
// Imposta il valore della larghezza del bordo su 0
border.Width = 0;
// Imposta il bordo per LinkAnnotation
link.Border = border;
// Specificare il tipo di collegamento come URI remoto
link.Action = new GoToURIAction("www.aspose.com");
// Aggiungere un'annotazione di collegamento alla raccolta di annotazioni della prima pagina del file PDF
page.Annotations.Add(link);
// Crea annotazione di testo libero
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// Stringa da aggiungere come testo libero
textAnnotation.Contents = "Link to Aspose website";
// Imposta il bordo per l'annotazione del testo libero
textAnnotation.Border = border;
// Aggiungere l'annotazione FreeText alla raccolta di annotazioni della prima pagina del documento
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// Salva il documento aggiornato
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## Conclusione

Congratulazioni! Ora hai una guida passo-passo per aggiungere collegamenti ipertestuali con Aspose.PDF per .NET. Puoi usare questo codice per creare collegamenti interattivi nei tuoi documenti PDF.

### FAQ per aggiungere un collegamento ipertestuale nel file PDF

#### D: Perché dovrei prendere in considerazione l'aggiunta di collegamenti ipertestuali ai miei file PDF?

R: Aggiungere collegamenti ipertestuali ai file PDF migliora l'esperienza utente consentendo ai lettori di navigare facilmente verso altre pagine, siti Web o destinazioni all'interno del documento. Fornisce un modo semplice per accedere a risorse aggiuntive o informazioni correlate.

#### D: Aspose.PDF per .NET è adatto ai principianti?

R: Sì, Aspose.PDF per .NET è adatto ai principianti. Il tutorial passo dopo passo fornito in questa guida semplifica il processo di aggiunta di collegamenti ipertestuali ai file PDF, rendendolo accessibile a sviluppatori con diversi livelli di competenza.

#### D: Posso personalizzare l'aspetto dei collegamenti ipertestuali?

R: Assolutamente! Aspose.PDF per .NET offre opzioni di personalizzazione per l'aspetto dell'hyperlink, tra cui colore del testo, stile e formattazione. Ciò consente di adattare gli hyperlink al design generale del documento.

#### D: I collegamenti ipertestuali sono supportati in tutti i tipi di documenti PDF?

R: Sì, è possibile aggiungere collegamenti ipertestuali a vari tipi di documenti PDF, inclusi documenti basati su testo, immagini e file multimediali. Aspose.PDF per .NET garantisce che i collegamenti ipertestuali siano funzionali in diversi formati PDF.

#### D: Quali altre funzionalità offre Aspose.PDF per .NET?

R: Aspose.PDF per .NET è una libreria robusta che fornisce un'ampia gamma di funzionalità, tra cui generazione, manipolazione, conversione ed estrazione di PDF. Supporta il lavoro con testo, immagini, annotazioni e altro, rendendolo uno strumento versatile per attività correlate a PDF.

#### D: È possibile aggiungere collegamenti ipertestuali a sezioni specifiche all'interno del documento?

 A: Sì, utilizzando il`LinkAnnotation` annotazione, puoi creare collegamenti ipertestuali che indirizzano gli utenti a sezioni specifiche all'interno del documento PDF. Questa funzionalità è particolarmente utile per creare un indice interattivo o collegamenti di riferimento.

#### D: Esistono delle limitazioni all'aggiunta di collegamenti ipertestuali nei file PDF?

R: Sebbene Aspose.PDF per .NET offra una funzionalità completa di collegamento ipertestuale, è importante assicurarsi che il contenuto collegato rimanga accessibile e aggiornato. I collegamenti ipertestuali a siti Web esterni devono essere verificati regolarmente per evitare collegamenti interrotti.

#### D: Posso creare collegamenti ipertestuali a file esterni utilizzando Aspose.PDF per .NET?

R: Sì, oltre agli URL Web, puoi creare collegamenti ipertestuali che portano a file esterni, come altri documenti PDF, immagini o file multimediali. Aspose.PDF per .NET offre la flessibilità di collegarsi a vari tipi di risorse.