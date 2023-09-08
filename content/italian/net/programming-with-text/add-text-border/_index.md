---
title: Aggiungi bordo di testo nel file PDF
linktitle: Aggiungi bordo di testo nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere un bordo di testo nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/programming-with-text/add-text-border/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di un bordo di testo nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere il bordo del testo, aggiungi la seguente direttiva using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: imposta la directory dei documenti
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: crea un nuovo oggetto Documento
 Istanziarne uno nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document pdfDocument = new Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungi una nuova pagina al documento utilizzando il file`Add` metodo del`Pages`collezione. Nel codice fornito, la nuova pagina viene assegnata alla variabile`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Passaggio 6: crea un TextFragment
 Creare un`TextFragment` oggetto e fornire il testo desiderato. Imposta la posizione del frammento di testo utilizzando`Position` proprietà. Nel codice fornito, il testo è impostato su "testo principale" e posizionato in (100, 600) nella pagina.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Passaggio 7: imposta le proprietà del testo
Personalizza le proprietà del testo come dimensione del carattere, tipo di carattere, colore di sfondo, colore di primo piano, ecc. Nel codice fornito, proprietà come dimensione del carattere, carattere, colore di sfondo, colore di primo piano e colore del tratto vengono impostate per il frammento di testo.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Passaggio 8: attiva il bordo del testo
 Per abilitare il bordo del testo, impostare il`DrawTextRectangleBorder`proprietà del frammento di testo`TextState` A`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Passaggio 9: aggiungi TextFragment alla pagina
 Usa il`TextBuilder` classe per aggiungere il file`TextFragment` opporsi alla pagina.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Passaggio 10: salva il documento PDF
 Salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Specificare il percorso del file di output impostato al passaggio 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Codice sorgente di esempio per Aggiungi bordo testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un nuovo oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina particolare
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Crea frammento di testo
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Imposta le proprietà del testo
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Imposta la proprietà StrokingColor per disegnare il bordo (traccia) attorno al rettangolo di testo
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Imposta il valore della proprietà DrawTextRectangleBorder su true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Salva il documento
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusione
Hai aggiunto con successo un bordo di testo al tuo documento PDF utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è l'obiettivo principale di questo tutorial?

R: Questo tutorial ti guida attraverso il processo di aggiunta di un bordo di testo a un file PDF utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari per raggiungere questo obiettivo.

#### D: Quali spazi dei nomi devo importare per questo tutorial?

R: Nel file di codice in cui desideri aggiungere il bordo del testo, importa i seguenti spazi dei nomi all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### D: Come posso specificare la directory dei documenti?

 A: Nel codice, individuare la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso creare un oggetto Document?

 R: Nel passaggio 4 creerai un'istanza di new`Document` oggetto utilizzando la seguente riga di codice:

```csharp
Document pdfDocument = new Document();
```

#### D: Come faccio ad aggiungere una pagina al documento?

 R: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### D: Come posso creare un TextFragment e impostarne la posizione?

 R: Nel passaggio 6 creerai un file`TextFragment`oggetto e impostarne la posizione sulla pagina utilizzando il comando`Position` proprietà:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### D: Come posso personalizzare le proprietà del testo, incluso il bordo del testo?

R: Nel passaggio 7 personalizzerai varie proprietà del testo come dimensione del carattere, tipo di carattere, colore di sfondo, colore di primo piano e bordo del testo:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### D: Come posso aggiungere TextFragment al documento PDF?

 R: Nel passaggio 9 utilizzerai il file`TextBuilder` classe per aggiungere il file`TextFragment` opporsi alla pagina:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### D: Come posso salvare il documento PDF risultante?

 R: Dopo aver aggiunto il testo con un bordo, utilizza il file`Save` metodo del`Document` oggetto per salvare il documento PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### D: Qual è il punto principale di questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come migliorare il tuo documento PDF aggiungendo un bordo di testo utilizzando Aspose.PDF per .NET. Ciò può essere particolarmente utile per enfatizzare contenuti di testo specifici all'interno dei file PDF.