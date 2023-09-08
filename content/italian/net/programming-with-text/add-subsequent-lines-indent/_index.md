---
title: Aggiungi il rientro delle righe successive nel file PDF
linktitle: Aggiungi il rientro delle righe successive nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere il rientro delle righe successive al testo nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-text/add-subsequent-lines-indent/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di righe successive con rientro al testo nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere il rientro delle righe successive, aggiungi la seguente direttiva using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: imposta la directory dei documenti
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: crea un nuovo oggetto Documento
 Istanziarne uno nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungi una nuova pagina al documento utilizzando il file`Add` metodo del`Pages`collezione. Nel codice fornito, la nuova pagina viene assegnata alla variabile`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Passaggio 6: crea un TextFragment con il rientro delle righe successive
 Istanziare a`TextFragment` oggetto e fornire il testo desiderato. Nel codice fornito, il testo è assegnato alla variabile`text` . Quindi inizializzare`TextFormattingOptions` per il`TextFragment` specificare il`SubsequentLinesIndent` valore.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Passaggio 7: aggiungi TextFragment alla pagina
 Aggiungi il`TextFragment` opporsi alla raccolta di paragrafi della pagina.

```csharp
page.Paragraphs.Add(text);
```

## Passaggio 8: ripetere i passaggi 6 e 7 per righe aggiuntive
Per aggiungere righe successive con lo stesso rientro, ripetere i passaggi 6 e 7 per ciascuna riga. Aggiorna il contenuto del testo secondo necessità.

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

## Passaggio 9: salva il documento PDF
 Salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Specificare il percorso del file di output.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Codice sorgente di esempio per aggiungere il rientro delle righe successive utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un nuovo oggetto documento
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Inizializza TextFormattingOptions per il frammento di testo e specifica il valore NextLinesIndent
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
Hai aggiunto con successo il rientro delle righe successive al testo utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è il focus di questo tutorial?

R: Questo tutorial fornisce una guida completa su come aggiungere il rientro delle righe successive al testo in un file PDF utilizzando la libreria Aspose.PDF per .NET. Include esempi di codice sorgente C# per illustrare i passaggi necessari per raggiungere questo obiettivo.

#### D: Quali spazi dei nomi devo importare per questo tutorial?

R: Nel file di codice in cui intendi aggiungere il rientro delle righe successive, importa i seguenti spazi dei nomi all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### D: Come posso specificare la directory dei documenti?

 A: Nel codice, individuare la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso creare un oggetto Document?

 R: Nel passaggio 4 creerai un'istanza di new`Document` oggetto utilizzando la seguente riga di codice:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### D: Come faccio ad aggiungere una pagina al documento?

 R: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### D: Come posso aggiungere il rientro delle righe successive al testo?

 R: Nel passaggio 6 creerai un file`TextFragment` oggetto e assegnargli il testo desiderato. Quindi, inizializzerai`TextFormattingOptions` per il`TextFragment` specificare il`SubsequentLinesIndent` valore:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### D: Come posso aggiungere TextFragment al documento PDF?

 R: Nel passaggio 7, aggiungerai il file`TextFragment` oggetto (`text`) alla raccolta paragrafi della pagina:

```csharp
page.Paragraphs.Add(text);
```

#### D: Posso ripetere la procedura per righe aggiuntive?

 R: Sì, al passaggio 8 puoi ripetere il processo per righe aggiuntive con lo stesso rientro creandone di nuove`TextFragment` oggetti e aggiungendoli alla raccolta paragrafi della pagina.

#### D: Come posso salvare il documento PDF risultante?

 R: Dopo aver aggiunto il testo con il rientro delle righe successive, utilizzare il comando`Save` metodo del`Document` oggetto per salvare il documento PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### D: Qual è il punto chiave di questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come migliorare la leggibilità del testo in un documento PDF aggiungendo il rientro delle righe successive utilizzando Aspose.PDF per .NET. Questa tecnica può essere utile per vari tipi di documenti e report.