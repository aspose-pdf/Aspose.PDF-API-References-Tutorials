---
title: Aggiungi rientro righe successive nel file PDF
linktitle: Aggiungi rientro righe successive nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere rientri alle righe successive del testo in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-text/add-subsequent-lines-indent/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di indentazioni di righe successive al testo nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui vuoi aggiungere il rientro alle righe successive, aggiungi la seguente direttiva using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory del documento
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: creare un nuovo oggetto Documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Passaggio 5: aggiungere una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando il`Add` metodo del`Pages`raccolta. Nel codice fornito, la nuova pagina è assegnata alla variabile`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Passaggio 6: creare un TextFragment con rientro delle righe successive
 Crea un'istanza`TextFragment` oggetto e fornire il testo desiderato. Nel codice fornito, il testo è assegnato alla variabile`text` Quindi, inizializzare`TextFormattingOptions` per il`TextFragment` specificare il`SubsequentLinesIndent` valore.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Passaggio 7: aggiungere TextFragment alla pagina
 Aggiungere il`TextFragment` oggetto alla raccolta di paragrafi della pagina.

```csharp
page.Paragraphs.Add(text);
```

## Passaggio 8: ripetere i passaggi 6 e 7 per le linee aggiuntive
Per aggiungere righe successive con lo stesso rientro, ripetere i passaggi 6 e 7 per ogni riga. Aggiornare il contenuto del testo come necessario.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Passaggio 9: Salvare il documento PDF
 Salvare il documento PDF utilizzando`Save` metodo del`Document` oggetto. Specificare il percorso del file di output.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Esempio di codice sorgente per Aggiungi rientro righe successive utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un nuovo oggetto documento
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Inizializza TextFormattingOptions per il frammento di testo e specifica il valore FollowingLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusione
Hai aggiunto con successo le righe successive indentate al testo usando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è l'obiettivo di questo tutorial?

R: Questo tutorial fornisce una guida completa su come aggiungere il rientro delle righe successive al testo in un file PDF utilizzando la libreria Aspose.PDF per .NET. Include esempi di codice sorgente C# per illustrare i passaggi richiesti per ottenere questo risultato.

#### D: Quali namespace devo importare per questo tutorial?

A: Nel file di codice in cui intendi aggiungere il rientro delle righe successive, importa i seguenti namespace all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### D: Come faccio a specificare la directory dei documenti?

 A: Nel codice, individua la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come si crea un oggetto Documento?

 A: Nel passaggio 4, creerai un nuovo`Document` oggetto utilizzando la seguente riga di codice:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### D: Come posso aggiungere una pagina al documento?

 A: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando`Add` metodo del`Pages` collezione:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### D: Come posso aggiungere un rientro alle righe successive del testo?

 A: Nel passaggio 6, creerai un`TextFragment` oggetto e assegnargli il testo desiderato. Quindi, inizializzerai`TextFormattingOptions` per il`TextFragment` specificare il`SubsequentLinesIndent` valore:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### D: Come posso aggiungere TextFragment al documento PDF?

 A: Nel passaggio 7, aggiungerai il`TextFragment` oggetto (`text`) alla raccolta di paragrafi della pagina:

```csharp
page.Paragraphs.Add(text);
```

#### D: Posso ripetere la procedura per altre linee?

 A: Sì, nel passaggio 8, puoi ripetere il processo per altre righe con lo stesso rientro creandone di nuove`TextFragment` oggetti e aggiungendoli alla raccolta di paragrafi della pagina.

#### D: Come posso salvare il documento PDF risultante?

 A: Dopo aver aggiunto il testo con le righe successive rientrate, utilizzare il`Save` metodo del`Document` oggetto per salvare il documento PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### D: Qual è il messaggio più importante da trarre da questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come migliorare la leggibilità del testo in un documento PDF aggiungendo rientri alle righe successive tramite Aspose.PDF per .NET. Questa tecnica può essere utile per vari tipi di documenti e report.