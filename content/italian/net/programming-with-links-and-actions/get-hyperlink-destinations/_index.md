---
title: Ottieni le destinazioni dell'hyperlink nel file PDF
linktitle: Ottieni le destinazioni dell'hyperlink nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre le destinazioni dei collegamenti ipertestuali nei file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF per .NET è una potente libreria per manipolare ed estrarre informazioni in file PDF usando il linguaggio di programmazione C#. In questo tutorial, ci concentreremo sull'estrazione di destinazioni di hyperlink da un file PDF usando Aspose.PDF per .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo integrato (IDE) come Visual Studio.
- La libreria Aspose.PDF per .NET è installata sul computer.

## Fase 1: Impostazione dell'ambiente di sviluppo

Prima di iniziare a scrivere il codice, devi configurare il tuo ambiente di sviluppo creando un nuovo progetto C# nel tuo IDE preferito.

## Passaggio 2: importare i riferimenti Aspose.PDF

Per usare Aspose.PDF per .NET, devi aggiungere i riferimenti appropriati al tuo progetto. Segui i passaggi sottostanti per importare i riferimenti necessari:

1. Nel tuo progetto, fai clic con il pulsante destro del mouse su "Riferimenti" e seleziona "Aggiungi riferimento".
2. Nella finestra "Aggiungi riferimento", individua e seleziona i file DLL di Aspose.PDF per .NET.
3. Fare clic su "OK" per importare i riferimenti nel progetto.

## Passaggio 3: caricamento del file PDF

Prima di poter estrarre le destinazioni dei collegamenti ipertestuali, devi caricare il file PDF nella tua applicazione. Utilizza il seguente codice per caricare il file PDF:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carica il file PDF
Document document = new Document(dataDir + "input.pdf");
```

Assicuratevi di specificare il percorso corretto della directory del documento e del file PDF che desiderate elaborare.

## Fase 4: Navigazione tra le pagine del documento

Ora che il file PDF è caricato, devi scorrere tutte le pagine del documento. Questo ti permetterà di ottenere

ir le annotazioni di collegamento ipertestuale presenti in ogni pagina. Utilizzare il seguente codice per scorrere le pagine del documento:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Ottieni le annotazioni dei link di una pagina specifica
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Crea un elenco per memorizzare tutti i link
     IList<Annotation> list = selector. Selected;
     // Passa attraverso ogni elemento nell'elenco
     foreach(LinkAnnotation a in list)
     {
         // Stampa URL di destinazione
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Questo codice scorre ogni pagina del documento e seleziona le annotazioni di collegamento ipertestuale presenti in ogni pagina. Quindi memorizza queste annotazioni in un elenco e stampa l'URL di destinazione per ogni collegamento.

## Passaggio 5: Ottenere le destinazioni dei collegamenti ipertestuali

L'ultimo passaggio consiste nell'estrarre le destinazioni dell'hyperlink dalle annotazioni dell'hyperlink. Il seguente codice mostra come farlo:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Utilizza la destinazione come preferisci
     }
}
```

In questo codice, otteniamo ogni destinazione di collegamento ipertestuale dalle annotazioni di collegamento e memorizziamo la destinazione in una variabile. Puoi quindi utilizzare questa destinazione come desideri nella tua applicazione.

### Esempio di codice sorgente per ottenere destinazioni di collegamento ipertestuale utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il file PDF
	Document document = new Document(dataDir + "input.pdf");
	// Scorri tutte le pagine del PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Ottieni le annotazioni del collegamento da una pagina specifica
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Crea un elenco contenente tutti i link
		IList<Annotation> list = selector.Selected;
		// Scorrere l'elemento individuale all'interno dell'elenco
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

### Domande frequenti per ottenere destinazioni di collegamento ipertestuale in file PDF

#### D: Cos'è una destinazione di collegamento ipertestuale in un file PDF?

R: Una destinazione di collegamento ipertestuale in un file PDF è una posizione o un target specifico a cui punta un collegamento ipertestuale. Potrebbe essere un URL, una pagina all'interno dello stesso documento o un documento esterno.

#### D: In che modo l'estrazione delle destinazioni dei collegamenti ipertestuali può essere utile per l'analisi dei miei documenti PDF?

A: L'estrazione delle destinazioni degli hyperlink consente di identificare e catalogare tutti i target a cui puntano gli hyperlink all'interno di un documento PDF. Queste informazioni possono essere utili per la convalida dei contenuti, la verifica dei link e l'analisi dei dati.

#### D: In che modo Aspose.PDF per .NET aiuta a estrarre le destinazioni dei collegamenti ipertestuali?

A: Aspose.PDF per .NET fornisce potenti API per estrarre facilmente le destinazioni degli hyperlink. Questo tutorial illustra passo dopo passo come estrarre le destinazioni degli hyperlink usando C#.

#### D: Posso estrarre selettivamente le destinazioni dei collegamenti ipertestuali in base a determinati criteri?

R: Sì, puoi estrarre selettivamente le destinazioni dei collegamenti ipertestuali scorrendo le pagine del documento PDF e filtrando le annotazioni dei collegamenti ipertestuali desiderate in base ai tuoi criteri.

#### D: È possibile estrarre le destinazioni dei collegamenti ipertestuali dai documenti PDF protetti da password?

R: Aspose.PDF per .NET può estrarre le destinazioni dei collegamenti ipertestuali dai documenti PDF protetti da password, a condizione che vengano fornite le credenziali di autenticazione necessarie all'apertura del documento.

#### D: Come posso utilizzare le destinazioni dei collegamenti ipertestuali estratte nella mia applicazione?

R: Dopo aver estratto le destinazioni dei collegamenti ipertestuali, puoi utilizzarle per eseguire varie azioni, come la convalida degli URL dei collegamenti, la creazione di report o l'implementazione di una navigazione personalizzata.

#### D: Ci sono delle limitazioni quando si estraggono le destinazioni dei collegamenti ipertestuali?

R: Sebbene l'estrazione della destinazione dell'hyperlink sia potente, è essenziale considerare la struttura del documento PDF. Gli hyperlink incorporati in grafica complessa o contenuti multimediali potrebbero richiedere una gestione aggiuntiva.

#### D: Posso estrarre altri attributi degli hyperlink, come i tipi di collegamento o le coordinate?

R: Il tutorial si concentra sull'estrazione delle destinazioni degli hyperlink. Tuttavia, puoi fare riferimento alla documentazione ufficiale di Aspose.PDF per esplorare le funzionalità avanzate, tra cui l'estrazione di tipi di link e coordinate.