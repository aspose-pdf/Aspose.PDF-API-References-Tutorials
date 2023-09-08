---
title: Cancellare le parole
linktitle: Cancellare le parole
second_title: Aspose.PDF per riferimento all'API .NET
description: Questo articolo fornisce una guida passo passo per l'utilizzo di Aspose.PDF per la funzione Barra parole di .NET, inclusa guida passo passo e spiegazioni
type: docs
weight: 150
url: /it/net/annotations/strikeoutwords/
---
Aspose.PDF per .NET è una libreria di manipolazione ed elaborazione di documenti PDF che fornisce varie funzionalità per creare, modificare e convertire file PDF. Una delle funzionalità utili fornite da Aspose.PDF è la possibilità di cancellare parole o frasi in un documento PDF utilizzando il codice sorgente C#. In questo articolo, forniremo una guida passo passo su come cancellare le parole utilizzando Aspose.PDF per .NET.

## Passaggio 1: caricamento del documento PDF
Il primo passo è caricare il documento PDF che desideri modificare. In questo tutorial, caricheremo un documento PDF denominato "input.pdf" dalla cartella "YOUR DOCUMENT DIRECTORY". 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Passaggio 2: ricerca di frammenti di testo
Per cancellare parole o frasi specifiche nel documento PDF, devi prima cercarle. Aspose.PDF fornisce una classe TextFragmentAbsorber che può essere utilizzata per cercare un frammento di testo specifico nel documento PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

Nel codice sopra, stiamo cercando il frammento di testo "Estoque" nel documento PDF. Puoi modificarlo per cercare qualsiasi altra parola o frase che desideri cancellare.

## Passaggio 3: eliminare i frammenti di testo
Dopo aver trovato i frammenti di testo, il passo successivo è cancellarli. Aspose.PDF fornisce una classe StrikeOutAnnotation che può essere utilizzata per creare un'annotazione barrata per il frammento di testo. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

Nel codice sopra, stiamo creando un'annotazione barrata per ogni frammento di testo che abbiamo trovato. Stiamo impostando anche l'opacità, il bordo e il colore dell'annotazione barrata.

## Passaggio 4: salvataggio del documento PDF modificato
Dopo aver cancellato i frammenti di testo, salva il documento modificato.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Codice sorgente di esempio per Barrare le parole utilizzando Aspose.PDF per .NET


```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document document = new Document(dataDir + "input.pdf");

// Crea un'istanza TextFragment Absorber per cercare un particolare frammento di testo
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Scorrere le pagine del documento PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Ottieni la prima pagina del documento PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Crea una raccolta di testo assorbito
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Ripetere la raccolta sopra
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Ottieni dimensioni rettangolari dell'oggetto TextFragment
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Crea un'istanza di StrikeOut Annotation
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Imposta l'opacità per l'annotazione
	strikeOut.Opacity = .80f;
	// Imposta il bordo per l'istanza di annotazione
	strikeOut.Border = new Border(strikeOut);
	// Imposta il colore dell'annotazione
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Aggiungi annotazione alla raccolta di annotazioni di TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come utilizzare Aspose.PDF per .NET per cancellare parole specifiche in un documento PDF. Seguendo la guida passo passo e utilizzando il codice sorgente C# fornito, puoi caricare facilmente un documento PDF, cercare frammenti di testo specifici e creare annotazioni barrate per contrassegnare e barrare visivamente quelle parole. Aspose.PDF per .NET fornisce un modo semplice ed efficace per manipolare i documenti PDF a livello di codice, rendendolo uno strumento prezioso per gli sviluppatori che lavorano con file PDF nelle applicazioni .NET.

### Domande frequenti

#### D: Cos'è Aspose.PDF per .NET?

R: Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, modificare e manipolare documenti PDF a livello di codice nelle applicazioni .NET. Fornisce un'ampia gamma di funzionalità per lavorare con file PDF, tra cui l'estrazione del testo, la gestione delle annotazioni, la compilazione dei moduli e molto altro.

#### D: Posso utilizzare Aspose.PDF per .NET per cancellare parole specifiche in un documento PDF?

R: Sì, Aspose.PDF per .NET fornisce funzionalità per cercare frammenti di testo specifici in un documento PDF e quindi creare annotazioni barrate per contrassegnare visivamente e cancellare quelle parole.

#### D: Come posso specificare il testo che voglio barrare nel documento PDF?

 R: Per specificare il testo che vuoi cancellare, puoi usare il`TextFragmentAbsorber` classe fornita da Aspose.PDF per .NET. Ti consente di cercare un frammento di testo specifico nel documento PDF in base ai criteri desiderati.

#### D: Posso personalizzare l'aspetto dell'annotazione barrata?

R: Sì, puoi personalizzare varie proprietà dell'annotazione barrata, come l'opacità, lo stile del bordo e il colore. Ciò ti consente di personalizzare l'aspetto dell'annotazione barrata in base alle tue esigenze specifiche.