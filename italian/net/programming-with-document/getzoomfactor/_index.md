---
title: Ottieni il fattore di zoom nel file PDF
linktitle: Ottieni il fattore di zoom nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per ottenere il fattore di zoom nel file PDF con questa guida dettagliata.
type: docs
weight: 210
url: /it/net/programming-with-document/getzoomfactor/
---
Aspose.PDF per .NET è una libreria di manipolazione PDF che offre molte funzionalità per eseguire varie operazioni sui documenti PDF. Una di queste funzionalità è la possibilità di ottenere il fattore di zoom nel file PDF. In questo tutorial, spiegheremo come utilizzare Aspose.PDF per .NET per ottenere il fattore di zoom nel file PDF utilizzando il codice sorgente C#.


## Passaggio 1: creare un'istanza del nuovo oggetto Document

 Il primo passo per ottenere il fattore di zoom di un file PDF utilizzando Aspose.PDF per .NET è creare un'istanza di un nuovo`Document` oggetto. IL`Document` oggetto rappresenta un documento PDF che può essere caricato da un file o da un flusso.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza di un nuovo oggetto Document
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Nel codice sopra, abbiamo creato a`Document` oggetto passando il percorso del file PDF al costruttore del file`Document` classe. Devi sostituire "YOUR DOCUMENT DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo file PDF.

## Passaggio 2: creare l'oggetto GoToAction

 Il prossimo passo è creare un file`GoToAction` oggetto. UN`GoToAction`oggetto rappresenta un'azione che va a una destinazione specifica in un documento PDF. Nel nostro caso, vogliamo ottenere il fattore di zoom del file PDF, quindi utilizzeremo il formato`OpenAction` proprietà del`Document` oggetto per ottenere il`GoToAction` oggetto.

```csharp
// Crea un oggetto GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 Nel codice sopra, abbiamo creato a`GoToAction` oggetto lanciando il`OpenAction` proprietà del`Document` opporsi a`GoToAction`.

## Passaggio 3: ottieni il fattore di zoom del file PDF

 Il terzo passaggio consiste nell'ottenere il fattore di zoom del file PDF. Possiamo ottenere il fattore di zoom del file PDF accedendo al file`Destination` proprietà del`GoToAction` oggetto e quindi trasmetterlo a`XYZExplicitDestination` . IL`XYZExplicitDestination` class rappresenta una destinazione in un documento PDF che specifica le coordinate e il fattore di zoom a cui andare.

```csharp
// Ottieni il fattore di zoom del file PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valore di zoom del documento;
```

 Nel codice sopra, abbiamo avuto accesso a`Destination` proprietà del`GoToAction` oggetto e quindi eseguirne il cast`XYZExplicitDestination` . Successivamente, abbiamo effettuato l'accesso al file`Zoom` proprietà del`XYZExplicitDestination` oggetto per ottenere il fattore di zoom del file PDF.

## Passaggio 4: emettere il fattore di zoom

 Il passaggio finale consiste nell'output del fattore di zoom del file PDF. Possiamo usare il`System.Console.WriteLine`

```csharp
// Ottieni il fattore di zoom del file PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valore di zoom del documento;
```        

### Codice sorgente di esempio per ottenere il fattore di zoom utilizzando Aspose.PDF per .NET

Ecco il codice sorgente di esempio completo per Ottieni fattore di zoom utilizzando Aspose.PDF per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza di un nuovo oggetto Document
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Crea un oggetto GoToAction
GoToAction action = doc.OpenAction as GoToAction;

// Ottieni il fattore di zoom del file PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valore di zoom del documento;
```

## Conclusione

In questo tutorial, abbiamo esplorato come utilizzare Aspose.PDF per .NET per ottenere il fattore di zoom di un file PDF. Il fattore di zoom è un aspetto cruciale di un documento PDF, in quanto determina la dimensione di visualizzazione iniziale quando viene aperto in un visualizzatore. Accedendo e utilizzando il fattore di zoom, gli sviluppatori possono personalizzare l'esperienza visiva per gli utenti finali. Aspose.PDF per .NET fornisce un'API semplice ed efficace per recuperare il fattore di zoom e altre informazioni relative alla navigazione da un documento PDF, consentendo agli sviluppatori di creare applicazioni PDF ricche di funzionalità e interattive.

### Domande frequenti per ottenere il fattore di zoom nel file PDF

#### D: Qual è il fattore di zoom in un file PDF?

R: Il fattore di zoom in un file PDF si riferisce al livello di ingrandimento applicato al documento quando viene visualizzato. Determina la dimensione di visualizzazione iniziale del file PDF sullo schermo. Un fattore di zoom di 1,0 rappresenta la dimensione effettiva (100% di zoom), mentre un fattore di zoom maggiore di 1,0 rappresenta un ingrandimento e un fattore di zoom inferiore a 1,0 rappresenta una riduzione.

#### D: Come posso utilizzare le informazioni sul fattore di zoom nella mia applicazione?

R: È possibile utilizzare le informazioni sul fattore di zoom per personalizzare la dimensione di visualizzazione iniziale di un documento PDF quando viene aperto in un visualizzatore. Ad esempio, è possibile impostare un fattore di zoom specifico per garantire che il PDF venga visualizzato con una dimensione particolare o per adattare l'intera pagina alla finestra del visualizzatore.

#### D: Posso modificare il fattore di zoom di un documento PDF a livello di programmazione utilizzando Aspose.PDF per .NET?

 A: Sì, è possibile modificare il fattore di zoom di un documento PDF in modo programmatico utilizzando Aspose.PDF per .NET. È possibile impostare il fattore di zoom per azioni specifiche, ad esempio`GoToAction` O`GoToRemoteAction`per controllare la modalità di visualizzazione del documento quando l'utente interagisce con collegamenti o segnalibri.

#### D: Esistono altri modi per navigare in posizioni specifiche in un documento PDF utilizzando Aspose.PDF per .NET?

 A: Sì, Aspose.PDF per .NET fornisce varie funzionalità per navigare in posizioni specifiche in un documento PDF. Oltre ad usare`GoToAction` , puoi usare altre azioni come`GoToURIAction` per aprire un URL,`GoToEmbeddedAction` per passare ai file incorporati e`GoToNamedAction` per andare a destinazioni denominate all'interno del documento PDF.