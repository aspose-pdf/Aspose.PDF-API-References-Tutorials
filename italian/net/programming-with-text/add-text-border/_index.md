---
title: Aggiungi bordo del testo
linktitle: Aggiungi bordo del testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere un bordo di testo a un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/programming-with-text/add-text-border/
---

Questo tutorial ti guiderà attraverso il processo di aggiunta di un bordo di testo utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di disporre di quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato nel tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere il bordo del testo, aggiungi la seguente direttiva using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory dei documenti
 Nel codice, individuare la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i documenti.

## Passaggio 4: creare un nuovo oggetto documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document pdfDocument = new Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione. Nel codice fornito, la nuova pagina è assegnata alla variabile`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Passaggio 6: creare un frammento di testo
 Creare un`TextFragment`oggetto e fornire il testo desiderato. Impostare la posizione del frammento di testo utilizzando il`Position` proprietà. Nel codice fornito, il testo è impostato su "testo principale" e posizionato a (100, 600) nella pagina.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Passaggio 7: imposta le proprietà del testo
Personalizza le proprietà del testo come dimensione del carattere, tipo di carattere, colore di sfondo, colore di primo piano, ecc. Nel codice fornito, proprietà come dimensione del carattere, carattere, colore di sfondo, colore di primo piano e colore del tratto sono impostate per il frammento di testo.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Passaggio 8: abilita il bordo del testo
 Per abilitare il bordo del testo, impostare il`DrawTextRectangleBorder` proprietà del frammento di testo`TextState` A`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Passaggio 9: aggiungere il TextFragment alla pagina
 Usa il`TextBuilder` classe per aggiungere il`TextFragment` opporsi alla pagina.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Passaggio 10: salvare il documento PDF
 Salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Specificare il percorso del file di output impostato nel passaggio 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Esempio di codice sorgente per Aggiungi bordo di testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un nuovo oggetto documento
Document pdfDocument = new Document();
// Ottieni una pagina particolare
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Crea un frammento di testo
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Imposta le proprietà del testo
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Imposta la proprietà StrokingColor per disegnare il bordo (tratto) attorno al rettangolo di testo
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