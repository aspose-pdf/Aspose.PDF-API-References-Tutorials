---
title: Estrai il testo evidenziato nel file PDF
linktitle: Estrai il testo evidenziato nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come estrarre il testo evidenziato nel file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.
type: docs
weight: 60
url: /it/net/annotations/extracthighlightedtext/
---
Per estrarre il testo evidenziato nel file PDF, è possibile utilizzare Aspose.PDF per l'API .NET. Questa API fornisce un modo semplice per recuperare tutto il testo che è stato evidenziato in un documento.

## Passaggio 1: caricare il documento PDF

 Il primo passaggio nell'estrazione del testo evidenziato nel file PDF consiste nel caricare il documento utilizzando Aspose.PDF per l'API .NET. Puoi farlo creando una nuova istanza del file`Document` class e passando il percorso al documento PDF come parametro. 

```csharp
// Il percorso della directory dei documenti.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Passaggio 2: scorrere tutte le annotazioni

 Il passaggio successivo consiste nel scorrere tutte le annotazioni nel documento PDF. Puoi farlo usando un`foreach` ciclo, in questo modo:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Il codice va qui
}
```

## Passaggio 3: filtra le annotazioni di markup del testo

 Dentro il`foreach` loop, dovrai filtrare tutte le annotazioni che non sono annotazioni di markup di testo. Puoi farlo controllando se l'annotazione è un'istanza di`TextMarkupAnnotation` classe.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Il codice va qui
}
```

## Passaggio 4: recupera i frammenti di testo evidenziati

 Dopo aver filtrato tutte le annotazioni di markup del testo, puoi recuperare i frammenti di testo evidenziati per ciascuna annotazione. Puoi farlo chiamando il`GetMarkedTextFragments()` metodo sul`TextMarkupAnnotation` oggetto.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Passaggio 5: visualizza il testo evidenziato

 Infine, puoi mostrare all'utente il testo evidenziato. Puoi farlo scorrendo ciascuno di essi`TextFragment` oggetto nel`TextFragmentCollection` e chiamando il`Text` proprietà.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Esempio di codice sorgente per Estrai testo evidenziato utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## Conclusione

In questo tutorial, abbiamo esplorato come estrarre il testo evidenziato da un documento PDF utilizzando Aspose.PDF per .NET. Seguendo la guida dettagliata e utilizzando il codice sorgente C# fornito, gli sviluppatori possono facilmente estrarre e gestire il testo evidenziato nei loro documenti PDF.

### Domande frequenti per estrarre il testo evidenziato nel file PDF

#### D: Cosa sono le annotazioni di markup del testo in un documento PDF?

R: Le annotazioni di markup del testo sono annotazioni che evidenziano o contrassegnano un testo specifico in un documento PDF. Esempi di annotazioni di markup del testo includono evidenziazioni, sottolineature e barrature.

#### D: Posso estrarre il testo da altri tipi di annotazioni utilizzando Aspose.PDF per .NET?

R: Sì, Aspose.PDF per .NET fornisce vari metodi per estrarre il testo da diversi tipi di annotazioni, incluse annotazioni di markup di testo, annotazioni di testo libero e altro.

#### D: Aspose.PDF per .NET supporta l'estrazione di testo da file PDF protetti da password?

R: Sì, Aspose.PDF per .NET supporta l'estrazione di testo da file PDF protetti da password. È necessario fornire la password corretta quando si carica il documento PDF utilizzando il file`Document` classe.

#### D: Posso filtrare il testo evidenziato in base ad altri criteri, come il colore o l'autore?

R: Sì, puoi filtrare il testo evidenziato in base ad altri criteri, come colore, autore o data di creazione. Aspose.PDF per .NET fornisce metodi per accedere e filtrare le annotazioni in base alle loro proprietà.

#### D: È possibile salvare il testo evidenziato estratto in un file separato?

R: Sì, puoi salvare il testo evidenziato estratto in un file separato o archiviarlo in una struttura dati per ulteriori elaborazioni o analisi.
