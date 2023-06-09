---
title: Aggiungi descrizione comandi al testo
linktitle: Aggiungi descrizione comandi al testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere suggerimenti al testo in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 90
url: /it/net/programming-with-text/add-tooltip-to-text/
---

Questo tutorial ti guiderà attraverso il processo di aggiunta di suggerimenti al testo in un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di disporre di quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato nel tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere suggerimenti al testo, aggiungi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory dei documenti
 Nel codice, individuare la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i documenti.

## Passaggio 4: crea un documento di esempio con il testo
 Crea un nuovo`Document` oggetto e aggiungere pagine con frammenti di testo. Nel codice fornito, due frammenti di testo vengono aggiunti al documento con il rispettivo testo di suggerimento.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Passaggio 5: apri il documento e trova i frammenti di testo
 Caricare il documento creato utilizzando il file`Document` costruttore e trova i frammenti di testo che necessitano di descrizioni comandi utilizzando`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Passaggio 6: aggiungi suggerimenti ai frammenti di testo
 Passa attraverso i frammenti di testo estratti e crea pulsanti invisibili nelle loro posizioni. Assegna il testo della descrizione comandi desiderato al file`AlternateName` proprietà del`ButtonField`. Aggiungi i campi pulsante al modulo del documento.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Passaggio 7: ripetere per frammenti di testo aggiuntivi con descrizioni comandi lunghe
Ripeti i passaggi 5 e 6 per i frammenti di testo con descrizioni comandi lunghe. Modificare i criteri di ricerca e il testo del tooltip di conseguenza.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Passaggio 8: salvare il documento modificato
 Salvare il documento PDF modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
document. Save(outputFile);
```

### Esempio di codice sorgente per Aggiungi descrizione comandi al testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Crea un documento di esempio con il testo
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Apri documento con testo
Document document = new Document(outputFile);
// Crea un oggetto TextAbsorber per trovare tutte le frasi che corrispondono all'espressione regolare
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Accetta l'assorbitore per le pagine del documento
document.Pages.Accept(absorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragments = absorber.TextFragments;
// Passa attraverso i frammenti
foreach (TextFragment fragment in textFragments)
{
	//Crea pulsante invisibile sulla posizione del frammento di testo
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Il valore AlternateName verrà visualizzato come suggerimento da un'applicazione visualizzatore
	field.AlternateName = "Tooltip for text.";
	// Aggiungi campo pulsante al documento
	document.Form.Add(field);
}
// Il prossimo sarà un esempio di tooltip molto lungo
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Imposta un testo molto lungo
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Salva documento
document.Save(outputFile);
```

## Conclusione
Hai aggiunto correttamente i suggerimenti al testo in un documento PDF utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.