---
title: Aggiungi bordo testo nel file PDF
linktitle: Aggiungi bordo testo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere un bordo di testo in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/programming-with-text/add-text-border/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di un bordo di testo in un file PDF usando Aspose.PDF per .NET. Il codice sorgente C# fornito dimostra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui vuoi aggiungere il bordo del testo, aggiungi la seguente direttiva using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory del documento
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: creare un nuovo oggetto Documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document pdfDocument = new Document();
```

## Passaggio 5: aggiungere una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando il`Add` metodo del`Pages`raccolta. Nel codice fornito, la nuova pagina è assegnata alla variabile`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Passaggio 6: creare un TextFragment
 Crea un`TextFragment` oggetto e fornire il testo desiderato. Imposta la posizione del frammento di testo utilizzando`Position` proprietà. Nel codice fornito, il testo è impostato su "testo principale" e posizionato a (100, 600) sulla pagina.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Passaggio 7: impostare le proprietà del testo
Personalizza le proprietà del testo, come dimensione del carattere, tipo di carattere, colore di sfondo, colore di primo piano, ecc. Nel codice fornito, proprietà come dimensione del carattere, carattere, colore di sfondo, colore di primo piano e colore del tratto sono impostate per il frammento di testo.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Passaggio 8: abilitare il bordo del testo
 Per abilitare il bordo del testo, impostare`DrawTextRectangleBorder`proprietà del frammento di testo`TextState` A`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Passaggio 9: aggiungere TextFragment alla pagina
 Utilizzare il`TextBuilder` classe per aggiungere il`TextFragment` oggetto alla pagina.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Passaggio 10: Salvare il documento PDF
 Salvare il documento PDF utilizzando`Save` metodo del`Document` oggetto. Specifica il percorso del file di output impostato nel passaggio 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Esempio di codice sorgente per Aggiungi bordo testo utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un nuovo oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina specifica
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Crea frammento di testo
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Imposta le proprietà del testo
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Imposta la proprietà StrokingColor per disegnare il bordo (stroking) attorno al rettangolo di testo
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Imposta il valore della proprietà DrawTextRectangleBorder su true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Salva il documento
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusione
Hai aggiunto con successo un bordo di testo al tuo documento PDF usando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è l'obiettivo principale di questo tutorial?

R: Questo tutorial ti guida attraverso il processo di aggiunta di un bordo di testo a un file PDF utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari per ottenere questo risultato.

#### D: Quali namespace devo importare per questo tutorial?

A: Nel file di codice in cui vuoi aggiungere il bordo del testo, importa i seguenti namespace all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### D: Come faccio a specificare la directory dei documenti?

 A: Nel codice, individua la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come si crea un oggetto Documento?

 A: Nel passaggio 4, creerai un nuovo`Document` oggetto utilizzando la seguente riga di codice:

```csharp
Document pdfDocument = new Document();
```

#### D: Come posso aggiungere una pagina al documento?

 A: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando`Add` metodo del`Pages` collezione:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### D: Come faccio a creare un TextFragment e a impostarne la posizione?

 A: Nel passaggio 6, creerai un`TextFragment`oggetto e imposta la sua posizione sulla pagina utilizzando`Position` proprietà:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### D: Come posso personalizzare le proprietà del testo, incluso il bordo del testo?

A: Nel passaggio 7, personalizzerai varie proprietà del testo, come la dimensione del carattere, il tipo di carattere, il colore di sfondo, il colore di primo piano e il bordo del testo:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### D: Come posso aggiungere TextFragment al documento PDF?

 A: Nel passaggio 9, utilizzerai il`TextBuilder` classe per aggiungere il`TextFragment` oggetto alla pagina:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### D: Come posso salvare il documento PDF risultante?

 A: Dopo aver aggiunto il testo con un bordo, utilizzare il`Save` metodo del`Document` oggetto per salvare il documento PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### D: Qual è la cosa più importante da imparare da questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come migliorare il tuo documento PDF aggiungendo un bordo di testo usando Aspose.PDF per .NET. Questo può essere particolarmente utile per enfatizzare contenuti di testo specifici nei tuoi file PDF.