---
title: Crea collegamento al documento
linktitle: Crea collegamento al documento
second_title: Riferimento API Aspose.PDF per .NET
description: Crea facilmente collegamenti ad altri documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-links-and-actions/create-document-link/
---
Il collegamento a un altro documento in un file PDF consente di creare collegamenti cliccabili che reindirizzano gli utenti ad altri documenti PDF. Con Aspose.PDF per .NET, è possibile creare facilmente tali collegamenti seguendo il seguente codice sorgente:

## Passaggio 1: importare le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso per la cartella dei documenti

 In questo passaggio, devi specificare il percorso della cartella contenente il file PDF a cui vuoi aggiungere un collegamento a un altro documento. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel codice seguente con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: aprire il documento PDF

Ora apriremo il documento PDF al quale vogliamo aggiungere il collegamento a un altro documento utilizzando il seguente codice:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Passaggio 4: creare il collegamento a un altro documento

 In questo passaggio creeremo il collegamento ad un altro documento utilizzando il`LinkAnnotation` annotazione. Specifichiamo le coordinate e l'area del collegamento, nonché l'azione di navigazione verso un documento esterno. Ecco il codice corrispondente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Passaggio 5: salvare il file aggiornato

Ora salviamo il file PDF aggiornato utilizzando il`Save` metodo del`document` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Esempio di codice sorgente per creare un collegamento al documento utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Crea collegamento
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Salva il documento aggiornato
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Conclusione

Congratulazioni! Ora hai una guida passo-passo per creare collegamenti ad altri documenti con Aspose.PDF per .NET. Puoi usare questo codice per creare collegamenti cliccabili nei tuoi file PDF, reindirizzando gli utenti ad altri documenti.

Per maggiori informazioni sulle funzionalità avanzate dei collegamenti interattivi, consultate la documentazione ufficiale di Aspose.PDF.

### FAQ per creare un collegamento al documento

#### D: Cosa sono i collegamenti ai documenti nei file PDF?

R: I link ai documenti nei file PDF sono link cliccabili che indirizzano gli utenti ad altri documenti PDF. Questi link migliorano la navigazione offrendo un modo efficiente per collegare contenuti correlati e facilitare un'esperienza di lettura fluida.

#### D: Quali vantaggi posso ottenere creando collegamenti ai documenti?

A: La creazione di collegamenti a documenti consente di stabilire connessioni tra diverse sezioni o argomenti all'interno dei documenti PDF. Questa funzionalità consente agli utenti di accedere facilmente a informazioni supplementari o materiali correlati.

#### D: In che modo Aspose.PDF per .NET supporta la creazione di collegamenti ai documenti?

R: Aspose.PDF per .NET semplifica il processo di creazione di link di documenti fornendo un set completo di API. Il tutorial passo dopo passo descritto in questa guida dimostra come aggiungere link di documenti ai file PDF.

#### D: Posso personalizzare l'aspetto dei collegamenti ai documenti?

A: Assolutamente! Aspose.PDF per .NET offre opzioni di personalizzazione per l'aspetto del collegamento al documento, inclusi colore, stile ed effetti hover. Puoi personalizzare l'aspetto per adattarlo al design del tuo documento.

#### D: È possibile creare collegamenti a sezioni o pagine specifiche all'interno di un altro documento?

R: Sì, puoi creare link che indirizzano gli utenti a pagine o sezioni specifiche all'interno di un altro documento PDF. Aspose.PDF per .NET offre la flessibilità di definire la posizione di destinazione all'interno del documento collegato.

#### D: Come posso assicurarmi che i link ai miei documenti siano funzionanti?

A: Seguendo il tutorial fornito e il codice di esempio, puoi creare con sicurezza link di documenti funzionali. Puoi testare i link aprendo il documento PDF generato e cliccando sui link.

#### D: Posso creare più collegamenti a documenti all'interno di un singolo file PDF?

 A: Certamente! Puoi creare più collegamenti a documenti all'interno di un singolo documento PDF utilizzando`LinkAnnotation` annotazione. Ciò consente di fornire agli utenti l'accesso a vari documenti correlati da sezioni diverse.

#### D: Ci sono delle limitazioni quando si collegano documenti esterni?

R: Quando si collegano documenti esterni, assicurarsi che i documenti collegati siano accessibili e posizionati nei percorsi specificati. È anche importante considerare i permessi utente e la compatibilità dei documenti collegati.

#### D: Posso creare collegamenti a documenti archiviati sul web o in repository online?

R: Mentre questo tutorial si concentra sul collegamento a documenti locali, Aspose.PDF per .NET supporta anche il collegamento a URL Web o repository online. Puoi adattare il codice fornito per creare collegamenti a documenti basati sul Web.