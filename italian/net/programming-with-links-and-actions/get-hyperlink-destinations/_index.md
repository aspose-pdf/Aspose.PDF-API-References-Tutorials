---
title: Ottieni destinazioni collegamento ipertestuale nel file PDF
linktitle: Ottieni destinazioni collegamento ipertestuale nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come estrarre le destinazioni dei collegamenti ipertestuali nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF per .NET è una potente libreria per la manipolazione e l'estrazione di informazioni in file PDF utilizzando il linguaggio di programmazione C#. In questo tutorial, ci concentreremo sull'estrazione delle destinazioni dei collegamenti ipertestuali da un file PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo integrato (IDE) come Visual Studio.
- La libreria Aspose.PDF per .NET installata sul tuo computer.

## Passaggio 1: configurazione dell'ambiente di sviluppo

Prima di iniziare a scrivere codice, devi configurare il tuo ambiente di sviluppo creando un nuovo progetto C# nel tuo IDE preferito.

## Passaggio 2: importa i riferimenti Aspose.PDF

Per utilizzare Aspose.PDF per .NET, è necessario aggiungere i riferimenti appropriati al progetto. Seguire i passaggi seguenti per importare i riferimenti necessari:

1. Nel tuo progetto, fai clic con il pulsante destro del mouse su "Riferimenti" e seleziona "Aggiungi riferimento".
2. Nella finestra "Aggiungi riferimento", individuare e selezionare i file DLL di Aspose.PDF per .NET.
3. Fare clic su "OK" per importare i riferimenti nel progetto.

## Passaggio 3: caricamento del file PDF

Prima di poter estrarre le destinazioni dei collegamenti ipertestuali, è necessario caricare il file PDF nell'applicazione. Utilizzare il seguente codice per caricare il file PDF:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carica il file PDF
Document document = new Document(dataDir + "input.pdf");
```

Assicurati di specificare il percorso corretto della directory dei documenti e del file PDF che desideri elaborare.

## Passaggio 4: navigazione tra le pagine del documento

Ora che il file PDF è caricato, devi scorrere tutte le pagine del documento. Questo ti permetterà di ottenere

ir le annotazioni dei collegamenti ipertestuali presenti in ogni pagina. Utilizzare il codice seguente per scorrere le pagine del documento:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Ottieni le annotazioni dei link di una pagina specifica
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Crea un elenco per memorizzare tutti i collegamenti
     IList<Annotation> list = selector. Selected;
     // Passa attraverso ogni elemento nell'elenco
     foreach(LinkAnnotation a in list)
     {
         // Stampa l'URL di destinazione
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Questo codice scorre ogni pagina del documento e seleziona le annotazioni del collegamento ipertestuale presenti su ogni pagina. Quindi memorizza queste annotazioni in un elenco e stampa l'URL di destinazione per ciascun collegamento.

## Passaggio 5: ottenere le destinazioni dei collegamenti ipertestuali

L'ultimo passaggio consiste nell'estrarre le destinazioni del collegamento ipertestuale dalle annotazioni del collegamento ipertestuale. Il codice seguente mostra come farlo:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Usa la destinazione come desideri
     }
}
```

In questo codice, otteniamo ogni destinazione del collegamento ipertestuale dalle annotazioni del collegamento e memorizziamo la destinazione in una variabile. È quindi possibile utilizzare questa destinazione come si desidera nella propria applicazione.

### Esempio di codice sorgente per Ottieni destinazioni collegamento ipertestuale utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il file PDF
	Document document = new Document(dataDir + "input.pdf");
	// Attraversa tutta la pagina del PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Ottieni le annotazioni dei collegamenti da una pagina specifica
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Crea una lista contenente tutti i link
		IList<Annotation> list = selector.Selected;
		// Scorri l'elemento invidiaul all'interno dell'elenco
		foreach (LinkAnnotation a in list)
		{
			// Stampa l'URL di destinazione
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### Domande frequenti per ottenere le destinazioni dei collegamenti ipertestuali nel file PDF

#### D: Cos'è una destinazione di collegamento ipertestuale in un file PDF?

R: Una destinazione di collegamento ipertestuale in un file PDF è una posizione specifica o una destinazione a cui punta un collegamento ipertestuale. Potrebbe essere un URL, una pagina all'interno dello stesso documento o un documento esterno.

#### D: In che modo l'estrazione delle destinazioni dei collegamenti ipertestuali può avvantaggiare l'analisi del mio documento PDF?

R: L'estrazione delle destinazioni dei collegamenti ipertestuali consente di identificare e catalogare tutte le destinazioni a cui puntano i collegamenti ipertestuali all'interno di un documento PDF. Queste informazioni possono essere utili per la convalida del contenuto, la verifica del collegamento e l'analisi dei dati.

#### D: In che modo Aspose.PDF per .NET aiuta a estrarre le destinazioni dei collegamenti ipertestuali?

R: Aspose.PDF per .NET fornisce potenti API per estrarre facilmente le destinazioni dei collegamenti ipertestuali. Questa esercitazione illustra dettagliatamente come estrarre le destinazioni dei collegamenti ipertestuali usando C#.

#### D: Posso estrarre in modo selettivo le destinazioni dei collegamenti ipertestuali in base a determinati criteri?

R: Sì, puoi estrarre in modo selettivo le destinazioni dei collegamenti ipertestuali scorrendo le pagine del documento PDF e filtrando le annotazioni dei collegamenti ipertestuali desiderate in base ai tuoi criteri.

#### D: È possibile estrarre destinazioni di collegamenti ipertestuali da documenti PDF protetti da password?

R: Aspose.PDF per .NET può estrarre destinazioni di collegamenti ipertestuali da documenti PDF protetti da password, purché tu fornisca le necessarie credenziali di autenticazione all'apertura del documento.

#### D: Come posso utilizzare le destinazioni dei collegamenti ipertestuali estratti nella mia applicazione?

R: Dopo aver estratto le destinazioni dei collegamenti ipertestuali, puoi utilizzarle per eseguire varie azioni, come la convalida degli URL dei collegamenti, la creazione di report o l'implementazione della navigazione personalizzata.

#### D: Ci sono limitazioni nell'estrazione delle destinazioni dei collegamenti ipertestuali?

R: Mentre l'estrazione della destinazione del collegamento ipertestuale è potente, è essenziale considerare la struttura del documento PDF. I collegamenti ipertestuali incorporati all'interno di grafica complessa o contenuti multimediali possono richiedere una gestione aggiuntiva.

#### D: Posso estrarre altri attributi dei collegamenti ipertestuali, come i tipi di collegamento o le coordinate?

R: Il tutorial è incentrato sull'estrazione delle destinazioni dei collegamenti ipertestuali. Tuttavia, puoi fare riferimento alla documentazione ufficiale di Aspose.PDF per esplorare funzionalità avanzate, inclusa l'estrazione di tipi di collegamento e coordinate.