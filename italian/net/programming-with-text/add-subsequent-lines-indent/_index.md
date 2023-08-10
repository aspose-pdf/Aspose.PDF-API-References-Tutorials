---
title: Aggiungi rientro righe successive
linktitle: Aggiungi rientro righe successive
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere il rientro delle righe successive al testo utilizzando Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-text/add-subsequent-lines-indent/
---

Questo tutorial ti guiderà attraverso il processo di aggiunta del rientro delle righe successive al testo utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di disporre di quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato nel tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere il rientro delle righe successive, aggiungi la seguente direttiva using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory dei documenti
 Nel codice, individuare la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i documenti.

## Passaggio 4: creare un nuovo oggetto documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione. Nel codice fornito, la nuova pagina è assegnata alla variabile`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Passaggio 6: crea un TextFragment con il rientro delle righe successive
 Istanza a`TextFragment` oggetto e fornire il testo desiderato. Nel codice fornito, il testo è assegnato alla variabile`text` . Quindi, inizializza`TextFormattingOptions` per il`TextFragment` e specificare il`SubsequentLinesIndent` valore.

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

## Passaggio 8: ripetere i passaggi 6 e 7 per le righe aggiuntive
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

## Passaggio 9: salvare il documento PDF
 Salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Specificare il percorso del file di output.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Codice sorgente di esempio per Aggiungi rientro righe successive utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un nuovo oggetto documento
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Inizializza TextFormattingOptions per il frammento di testo e specifica il valore di FollowingLinesIndent
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
Hai aggiunto correttamente il rientro delle righe successive al testo utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.