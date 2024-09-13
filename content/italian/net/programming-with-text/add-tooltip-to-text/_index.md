---
title: Aggiungi suggerimento al testo nel file PDF
linktitle: Aggiungi suggerimento al testo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere suggerimenti al testo in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 90
url: /it/net/programming-with-text/add-tooltip-to-text/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di tooltip al testo in un file PDF usando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui vuoi aggiungere suggerimenti al testo, aggiungi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory del documento
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: creare un documento di esempio con testo
 Crea un nuovo`Document`oggetto e aggiungi pagine con frammenti di testo. Nel codice fornito, due frammenti di testo vengono aggiunti al documento con il rispettivo testo di suggerimento.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Passaggio 5: aprire il documento e trovare i frammenti di testo
 Caricare il documento creato utilizzando il`Document` costruttore e trova i frammenti di testo che necessitano di suggerimenti utilizzando`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Passaggio 6: aggiungere suggerimenti ai frammenti di testo
 Passa attraverso i frammenti di testo estratti e crea pulsanti invisibili nelle loro posizioni. Assegna il testo tooltip desiderato al`AlternateName` proprietà del`ButtonField`Aggiungere i campi pulsante al modulo del documento.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Passaggio 7: ripetere per ulteriori frammenti di testo con suggerimenti lunghi
Ripetere i passaggi 5 e 6 per frammenti di testo con tooltip lunghi. Modificare i criteri di ricerca e il testo del tooltip di conseguenza.

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

## Passaggio 8: Salvare il documento modificato
 Salvare il documento PDF modificato utilizzando`Save` metodo del`Document` oggetto.

```csharp
document. Save(outputFile);
```

### Esempio di codice sorgente per Aggiungi suggerimento al testo utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Crea un documento di esempio con testo
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Apri documento con testo
Document document = new Document(outputFile);
//Crea un oggetto TextAbsorber per trovare tutte le frasi che corrispondono all'espressione regolare
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Accetta l'assorbitore per le pagine del documento
document.Pages.Accept(absorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragments = absorber.TextFragments;
// Fai un giro tra i frammenti
foreach (TextFragment fragment in textFragments)
{
	// Crea un pulsante invisibile sulla posizione del frammento di testo
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Il valore AlternateName verrà visualizzato come suggerimento da un'applicazione di visualizzazione
	field.AlternateName = "Tooltip for text.";
	// Aggiungere il campo pulsante al documento
	document.Form.Add(field);
}
// Il prossimo sarà un esempio di tooltip molto lungo
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Imposta testo molto lungo
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
// Salvare il documento
document.Save(outputFile);
```

## Conclusione
Hai aggiunto correttamente i tooltip al testo in un documento PDF usando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

## Domande frequenti

#### D: Qual è l'obiettivo di questo tutorial?

R: Questo tutorial si concentra sull'aggiunta di tooltip al testo all'interno di un file PDF utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari per ottenere questo risultato.

#### D: Quali namespace devono essere importati per questo tutorial?

A: Nel file di codice in cui vuoi aggiungere suggerimenti al testo, importa i seguenti namespace all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### D: Come faccio a specificare la directory dei documenti?

 A: Nel codice, trova la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come posso creare un documento di esempio con testo?

 A: Nel passaggio 4, creerai un nuovo`Document` oggetto e aggiungi pagine con frammenti di testo. Il codice fornito aggiunge due frammenti di testo con il rispettivo testo di suggerimento.

#### D: Come faccio ad aprire il documento e a trovare i frammenti di testo?

 A: Nel passaggio 5, caricherai il documento creato utilizzando`Document` costruttore e trova i frammenti di testo che richiedono suggerimenti utilizzando il`TextFragmentAbsorber`.

#### D: Come posso aggiungere suggerimenti ai frammenti di testo?

 A: Nel passaggio 6, scorrerai i frammenti di testo estratti e creerai pulsanti invisibili nelle loro posizioni. Il testo del tooltip è assegnato a`AlternateName` proprietà del`ButtonField`, che viene aggiunto al modulo del documento.

#### D: Come posso ripetere il procedimento per ulteriori frammenti di testo con tooltip lunghi?

A: Per frammenti di testo con tooltip lunghi, ripetere i passaggi 5 e 6. Modificare di conseguenza i criteri di ricerca e il testo del tooltip.

#### D: Come posso salvare il documento modificato?

 A: Nel passaggio 8, salverai il documento PDF modificato utilizzando`Save` metodo del`Document` oggetto.

#### D: Qual è la cosa più importante da imparare da questo tutorial?

R: Seguendo questo tutorial, hai imparato come migliorare il tuo documento PDF aggiungendo tooltip al testo usando Aspose.PDF per .NET. Questo può fornire preziose informazioni aggiuntive per i lettori quando interagiscono con il contenuto PDF.