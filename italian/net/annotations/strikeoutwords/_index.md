---
title: Cancellare le parole
linktitle: Cancellare le parole
second_title: Aspose.PDF per riferimento API .NET
description: Questo articolo fornisce una guida dettagliata all'utilizzo di Aspose.PDF per la funzione Barra parole di .NET, incluse guide e spiegazioni dettagliate
type: docs
weight: 150
url: /it/net/annotations/strikeoutwords/
---
Aspose.PDF per .NET è una libreria per la manipolazione e l'elaborazione di documenti PDF che fornisce varie funzionalità per creare, modificare e convertire file PDF. Una delle funzioni utili fornite da Aspose.PDF è la possibilità di barrare parole o frasi in un documento PDF utilizzando il codice sorgente C#. In questo articolo, forniremo una guida dettagliata su come cancellare le parole usando Aspose.PDF per .NET.

## Caricamento del documento PDF
Il primo passo è caricare il documento PDF che vuoi modificare. In questo tutorial, caricheremo un documento PDF denominato "input.pdf" dalla cartella "YOUR DOCUMENT DIRECTORY". 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Ricerca di frammenti di testo
Per eliminare parole o frasi specifiche nel documento PDF, devi prima cercarle. Aspose.PDF fornisce una classe TextFragmentAbsorber che può essere utilizzata per cercare un frammento di testo specifico nel documento PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

Nel codice sopra, stiamo cercando il frammento di testo "Estoque" nel documento PDF. Puoi modificarlo per cercare qualsiasi altra parola o frase che desideri barrare.

## Cancellare i frammenti di testo
Dopo aver trovato i frammenti di testo, il passo successivo è cancellarli. Aspose.PDF fornisce una classe StrikeOutAnnotation che può essere utilizzata per creare un'annotazione barrata per il frammento di testo. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

Nel codice sopra, stiamo creando un'annotazione barrata per ogni frammento di testo che abbiamo trovato. Stiamo anche impostando l'opacità, il bordo e il colore dell'annotazione barrata.

## Salvataggio del documento PDF modificato
Dopo aver eliminato i frammenti di testo, salvare il documento modificato.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Esempio di codice sorgente per barrare le parole utilizzando Aspose.PDF per .NET


```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document document = new Document(dataDir + "input.pdf");

// Crea un'istanza di TextFragment Absorber per cercare un particolare frammento di testo
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Scorri le pagine del documento PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Ottieni la prima pagina del documento PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Crea una raccolta di testo assorbito
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Itera sulla raccolta sopra
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Ottieni le dimensioni rettangolari dell'oggetto TextFragment
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
