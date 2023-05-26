---
title: Estrai testo evidenziato
linktitle: Estrai testo evidenziato
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come estrarre il testo evidenziato utilizzando Aspose.PDF per .NET con questa guida dettagliata.
type: docs
weight: 60
url: /it/net/annotations/extracthighlightedtext/
---
Per estrarre il testo evidenziato da un documento PDF, è possibile utilizzare l'API Aspose.PDF per .NET. Questa API fornisce un modo semplice per recuperare tutto il testo che è stato evidenziato in un documento.

## Passaggio 1: caricare il documento PDF

 Il primo passaggio nell'estrazione del testo evidenziato da un documento PDF consiste nel caricare il documento utilizzando Aspose.PDF per l'API .NET. Puoi farlo creando una nuova istanza del file`Document` class e passando il percorso al documento PDF come parametro. 

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

