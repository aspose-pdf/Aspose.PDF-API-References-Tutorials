---
title: Crea collegamento al documento
linktitle: Crea collegamento al documento
second_title: Aspose.PDF per riferimento all'API .NET
description: Crea facilmente collegamenti ad altri documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-links-and-actions/create-document-link/
---
Il collegamento a un altro documento in un file PDF consente di creare collegamenti selezionabili che reindirizzano gli utenti ad altri documenti PDF. Con Aspose.PDF per .NET, puoi facilmente creare tali collegamenti seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la necessaria direttiva sulle importazioni:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

In questo passaggio, devi specificare il percorso della cartella contenente il file PDF a cui desideri aggiungere un collegamento a un altro documento. Sostituire`"YOUR DOCUMENT DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF a cui vogliamo aggiungere il collegamento ad un altro documento utilizzando il seguente codice:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Passaggio 4: crea il collegamento a un altro documento

 In questo passaggio, creeremo il collegamento a un altro documento utilizzando il file`LinkAnnotation` annotazione. Specificheremo le coordinate e l'area del collegamento, nonché l'azione di navigazione verso un documento esterno. Ecco il codice corrispondente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Passaggio 5: salva il file aggiornato

 Ora salviamo il file PDF aggiornato utilizzando il file`Save` metodo del`document` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Codice sorgente di esempio per Crea collegamento documento utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
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
// Salva documento aggiornato
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per il collegamento ad altri documenti con Aspose.PDF per .NET. Puoi utilizzare questo codice per creare collegamenti cliccabili nei tuoi file PDF, reindirizzando gli utenti ad altri documenti.

Assicurati di controllare la documentazione ufficiale Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate dei collegamenti interattivi.

### Domande frequenti per la creazione del collegamento al documento

#### D: Cosa sono i collegamenti ai documenti nei file PDF?

R: I collegamenti ai documenti nei file PDF sono collegamenti selezionabili che indirizzano gli utenti ad altri documenti PDF. Questi collegamenti migliorano la navigazione fornendo un modo efficiente per collegare contenuti correlati e facilitare un'esperienza di lettura senza interruzioni.

#### D: Come posso trarre vantaggio dalla creazione di collegamenti a documenti?

R: La creazione di collegamenti a documenti ti consente di stabilire connessioni tra diverse sezioni o argomenti all'interno dei tuoi documenti PDF. Questa funzionalità consente agli utenti di accedere facilmente a informazioni supplementari o materiali correlati.

#### D: In che modo Aspose.PDF per .NET supporta la creazione di collegamenti a documenti?

R: Aspose.PDF per .NET semplifica il processo di creazione di collegamenti a documenti fornendo un set completo di API. Il tutorial passo passo descritto in questa guida mostra come aggiungere collegamenti a documenti ai tuoi file PDF.

#### D: Posso personalizzare l'aspetto dei collegamenti ai documenti?

R: Assolutamente! Aspose.PDF per .NET offre opzioni di personalizzazione per l'aspetto del collegamento del documento, inclusi colore, stile ed effetti al passaggio del mouse. Puoi personalizzare l'aspetto per adattarlo al design del tuo documento.

#### D: È possibile collegarsi a sezioni o pagine specifiche all'interno di un altro documento?

R: Sì, puoi creare collegamenti che indirizzano gli utenti a pagine o sezioni specifiche all'interno di un altro documento PDF. Aspose.PDF per .NET offre la flessibilità di definire la posizione di destinazione all'interno del documento collegato.

#### D: Come posso assicurarmi che i collegamenti ai miei documenti funzionino?

R: Seguendo il tutorial e il codice di esempio forniti, puoi creare con sicurezza collegamenti a documenti funzionali. È possibile testare i collegamenti aprendo il documento PDF generato e facendo clic sui collegamenti.

#### D: Posso creare più collegamenti a documenti all'interno di un singolo file PDF?

 R: Certamente! È possibile creare più collegamenti a documenti all'interno di un singolo documento PDF utilizzando il file`LinkAnnotation`annotazione. Ciò consente di fornire agli utenti l'accesso a vari documenti correlati da diverse sezioni.

#### D: Esistono limitazioni quando si collega a documenti esterni?

R: Quando si effettuano collegamenti a documenti esterni, assicurarsi che i documenti collegati siano accessibili e posizionati nei percorsi specificati. È inoltre importante considerare le autorizzazioni dell'utente e la compatibilità dei documenti collegati.

#### D: Posso collegarmi a documenti archiviati sul Web o in archivi online?

R: Sebbene questo tutorial si concentri sul collegamento a documenti locali, Aspose.PDF per .NET supporta anche il collegamento a URL Web o repository online. È possibile adattare il codice fornito per creare collegamenti a documenti basati sul Web.