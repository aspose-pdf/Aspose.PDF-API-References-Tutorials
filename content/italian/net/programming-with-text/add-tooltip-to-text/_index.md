---
title: Aggiungi descrizione comando al testo nel file PDF
linktitle: Aggiungi descrizione comando al testo nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere descrizioni comandi al testo nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 90
url: /it/net/programming-with-text/add-tooltip-to-text/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di descrizioni comandi al testo nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere descrizioni comando al testo, aggiungi le seguenti direttive using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Passaggio 3: imposta la directory dei documenti
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: crea un documento di esempio con testo
 Creane uno nuovo`Document` oggetto e aggiungere pagine con frammenti di testo. Nel codice fornito vengono aggiunti al documento due frammenti di testo con il rispettivo testo del tooltip.

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

## Passaggio 6: aggiungi descrizioni comandi ai frammenti di testo
 Passa in rassegna i frammenti di testo estratti e crea pulsanti invisibili nelle loro posizioni. Assegna il testo tooltip desiderato al file`AlternateName` proprietà del`ButtonField`. Aggiungi i campi del pulsante al modulo del documento.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Passaggio 7: ripetere l'operazione per ulteriori frammenti di testo con descrizioni comandi lunghe
Ripeti i passaggi 5 e 6 per i frammenti di testo con descrizioni comandi lunghe. Modifica i criteri di ricerca e il testo della descrizione comando di conseguenza.

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

## Passaggio 8: salva il documento modificato
 Salvare il documento PDF modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
document. Save(outputFile);
```

### Codice sorgente di esempio per Aggiungi descrizione comando al testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Crea un documento di esempio con testo
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Apri il documento con il testo
Document document = new Document(outputFile);
// Crea un oggetto TextAbsorber per trovare tutte le frasi che corrispondono all'espressione regolare
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Accettare l'assorbitore per le pagine del documento
document.Pages.Accept(absorber);
// Ottieni i frammenti di testo estratti
TextFragmentCollection textFragments = absorber.TextFragments;
// Passa in rassegna i frammenti
foreach (TextFragment fragment in textFragments)
{
	// Crea un pulsante invisibile sulla posizione del frammento di testo
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Il valore AlternateName verrà visualizzato come descrizione comando da un'applicazione visualizzatore
	field.AlternateName = "Tooltip for text.";
	// Aggiungi un campo pulsante al documento
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
Hai aggiunto con successo descrizioni comandi al testo in un documento PDF utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

## Domande frequenti

#### D: Qual è il focus di questo tutorial?

R: Questo tutorial si concentra sull'aggiunta di descrizioni comandi al testo all'interno di un file PDF utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari per raggiungere questo obiettivo.

#### D: Quali spazi dei nomi devono essere importati per questo tutorial?

R: Nel file di codice in cui desideri aggiungere descrizioni comando al testo, importa i seguenti spazi dei nomi all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### D: Come posso specificare la directory dei documenti?

 A: Nel codice, trova la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso creare un documento di esempio con testo?

 R: Nel passaggio 4 ne creerai uno nuovo`Document` oggetto e aggiungere pagine con frammenti di testo. Il codice fornito aggiunge due frammenti di testo con il rispettivo testo tooltip.

#### D: Come faccio ad aprire il documento e trovare i frammenti di testo?

 R: Nel passaggio 5, caricherai il documento creato utilizzando il file`Document` costruttore e trova i frammenti di testo che richiedono descrizioni comandi utilizzando il file`TextFragmentAbsorber`.

#### D: Come posso aggiungere descrizioni comandi ai frammenti di testo?

 R: Nel passaggio 6, scorrerai i frammenti di testo estratti e creerai pulsanti invisibili nelle loro posizioni. Il testo della descrizione comando è assegnato al file`AlternateName` proprietà del`ButtonField`che viene aggiunto al modulo del documento.

#### D: Come posso ripetere la procedura per ulteriori frammenti di testo con descrizioni comandi lunghe?

R: Per frammenti di testo con tooltip lunghi, ripetere i passaggi 5 e 6. Modificare di conseguenza i criteri di ricerca e il testo del tooltip.

#### D: Come posso salvare il documento modificato?

 R: Nel passaggio 8, salverai il documento PDF modificato utilizzando il file`Save` metodo del`Document` oggetto.

#### D: Qual è il punto principale di questo tutorial?

R: Seguendo questo tutorial, hai imparato come migliorare il tuo documento PDF aggiungendo descrizioni comandi al testo utilizzando Aspose.PDF per .NET. Ciò può fornire preziose informazioni aggiuntive ai lettori quando interagiscono con il contenuto PDF.