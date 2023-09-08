---
title: Ottieni destinazioni di collegamenti ipertestuali nel file PDF
linktitle: Ottieni destinazioni di collegamenti ipertestuali nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come estrarre le destinazioni dei collegamenti ipertestuali nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF per .NET è una potente libreria per manipolare ed estrarre informazioni in file PDF utilizzando il linguaggio di programmazione C#. In questo tutorial, ci concentreremo sull'estrazione delle destinazioni dei collegamenti ipertestuali da un file PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo integrato (IDE) come Visual Studio.
- La libreria Aspose.PDF per .NET installata sul tuo computer.

## Passaggio 1: configurazione dell'ambiente di sviluppo

Prima di iniziare a scrivere codice, devi configurare il tuo ambiente di sviluppo creando un nuovo progetto C# nel tuo IDE preferito.

## Passaggio 2: importa i riferimenti Aspose.PDF

Per utilizzare Aspose.PDF per .NET, è necessario aggiungere i riferimenti appropriati al tuo progetto. Seguire i passaggi seguenti per importare i riferimenti necessari:

1. Nel tuo progetto, fai clic con il pulsante destro del mouse su "Riferimenti" e seleziona "Aggiungi riferimento".
2. Nella finestra "Aggiungi riferimento", individuare e selezionare i file DLL di Aspose.PDF per .NET.
3. Fai clic su "OK" per importare i riferimenti nel tuo progetto.

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

ir le annotazioni dei collegamenti ipertestuali presenti su ogni pagina. Utilizzare il seguente codice per scorrere le pagine del documento:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Ottieni le annotazioni dei collegamenti di una pagina specifica
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Crea un elenco per memorizzare tutti i collegamenti
     IList<Annotation> list = selector. Selected;
     // Passa in rassegna ogni elemento dell'elenco
     foreach(LinkAnnotation a in list)
     {
         // Stampa l'URL di destinazione
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Questo codice scorre ogni pagina del documento e seleziona le annotazioni del collegamento ipertestuale presenti su ogni pagina. Quindi memorizza queste annotazioni in un elenco e stampa l'URL di destinazione per ciascun collegamento.

## Passaggio 5: acquisizione delle destinazioni dei collegamenti ipertestuali

L'ultimo passaggio consiste nell'estrarre le destinazioni dei collegamenti ipertestuali dalle annotazioni dei collegamenti ipertestuali. Il codice seguente mostra come farlo:

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

In questo codice, otteniamo ciascuna destinazione del collegamento ipertestuale dalle annotazioni del collegamento e memorizziamo la destinazione in una variabile. Potrai quindi utilizzare questa destinazione come desideri nella tua applicazione.

### Codice sorgente di esempio per Ottieni destinazioni collegamento ipertestuale utilizzando Aspose.PDF per .NET 
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
		// Ottieni le annotazioni del collegamento da una pagina particolare
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Crea un elenco contenente tutti i collegamenti
		IList<Annotation> list = selector.Selected;
		// Scorrere l'elemento invidiaul all'interno dell'elenco
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

### Domande frequenti per ottenere destinazioni di collegamenti ipertestuali nel file PDF

#### D: Cos'è la destinazione di un collegamento ipertestuale in un file PDF?

R: La destinazione di un collegamento ipertestuale in un file PDF è una posizione o destinazione specifica a cui punta un collegamento ipertestuale. Potrebbe essere un URL, una pagina all'interno dello stesso documento o un documento esterno.

#### D: In che modo l'estrazione delle destinazioni dei collegamenti ipertestuali può apportare vantaggi all'analisi dei documenti PDF?

R: L'estrazione delle destinazioni dei collegamenti ipertestuali consente di identificare e catalogare tutte le destinazioni a cui puntano i collegamenti ipertestuali all'interno di un documento PDF. Queste informazioni possono essere utili per la convalida del contenuto, la verifica dei collegamenti e l'analisi dei dati.

#### D: In che modo Aspose.PDF per .NET assiste nell'estrazione delle destinazioni dei collegamenti ipertestuali?

R: Aspose.PDF per .NET fornisce potenti API per estrarre facilmente le destinazioni dei collegamenti ipertestuali. Questa esercitazione illustra passo passo come estrarre le destinazioni dei collegamenti ipertestuali utilizzando C#.

#### D: Posso estrarre selettivamente le destinazioni dei collegamenti ipertestuali in base a determinati criteri?

R: Sì, puoi estrarre selettivamente le destinazioni dei collegamenti ipertestuali scorrendo le pagine del documento PDF e filtrando le annotazioni dei collegamenti ipertestuali desiderate in base ai tuoi criteri.

#### D: È possibile estrarre destinazioni di collegamenti ipertestuali da documenti PDF protetti da password?

R: Aspose.PDF per .NET può estrarre destinazioni di collegamenti ipertestuali da documenti PDF protetti da password purché si forniscano le credenziali di autenticazione necessarie all'apertura del documento.

#### D: Come posso utilizzare le destinazioni dei collegamenti ipertestuali estratti nella mia applicazione?

R: Una volta estratte le destinazioni dei collegamenti ipertestuali, puoi utilizzarle per eseguire varie azioni, come la convalida degli URL dei collegamenti, la creazione di report o l'implementazione della navigazione personalizzata.

#### D: Esistono limitazioni durante l'estrazione delle destinazioni dei collegamenti ipertestuali?

R: Sebbene l'estrazione della destinazione del collegamento ipertestuale sia potente, è essenziale considerare la struttura del documento PDF. I collegamenti ipertestuali incorporati in grafica complessa o contenuto multimediale potrebbero richiedere una gestione aggiuntiva.

#### D: Posso estrarre altri attributi dei collegamenti ipertestuali, come tipi di collegamento o coordinate?

R: Il tutorial si concentra sull'estrazione delle destinazioni dei collegamenti ipertestuali. Tuttavia, puoi fare riferimento alla documentazione ufficiale Aspose.PDF per esplorare funzionalità avanzate, inclusa l'estrazione di tipi di collegamento e coordinate.