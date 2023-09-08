---
title: Aggiungi testo trasparente nel file PDF
linktitle: Aggiungi testo trasparente nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere testo trasparente nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-text/add-transparent-text/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di testo trasparente a un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere testo trasparente, aggiungi le seguenti direttive using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Passaggio 3: imposta la directory dei documenti
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: crea una nuova istanza del documento
 Istanziarne uno nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungi una nuova pagina al documento utilizzando il file`Add` metodo del`Pages`collezione. Nel codice fornito, la nuova pagina viene assegnata alla variabile`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Passaggio 6: crea un oggetto grafico
 Creane uno nuovo`Graph` oggetto con una larghezza e un'altezza specifiche.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Passaggio 7: crea un rettangolo con trasparenza
 Crea un rettangolo con dimensioni specifiche e imposta il colore di riempimento su un colore trasparente utilizzando il`Color.FromRgb` metodo.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Passaggio 8: aggiungi l'oggetto Graph alla pagina
 Aggiungi il`Graph` opporsi alla raccolta di paragrafi della pagina.

```csharp
page.Paragraphs.Add(canvas);
```

## Passaggio 9: impostare la posizione per l'oggetto grafico
 Impostare il`IsChangePosition` proprietà del`Graph` opporsi a`false` per evitare che cambi posizione.

```csharp
canvas. IsChangePosition = false;
```

## Passaggio 10: crea un TextFragment con trasparenza
 Creare un`TextFragment` oggetto e impostarne il contenuto sul testo desiderato. Impostare il`ForegroundColor` proprietà del`TextState` a un colore con trasparenza utilizzando il`Color.FromArgb` metodo.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## Passaggio 11: salva il documento PDF
 Salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Codice sorgente di esempio per aggiungere testo trasparente utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea istanza del documento
Document doc = new Document();
// Crea una raccolta pagina per pagina di file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Crea oggetto grafico
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Crea un'istanza di rettangolo con determinate dimensioni
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Crea un oggetto colore dal canale colore Alpha
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Aggiungi rettangolo alla raccolta di forme dell'oggetto grafico
canvas.Shapes.Add(rect);
//Aggiungi un oggetto grafico alla raccolta di paragrafi dell'oggetto pagina
page.Paragraphs.Add(canvas);
// Imposta il valore per non modificare la posizione dell'oggetto grafico
canvas.IsChangePosition = false;
// Crea un'istanza TextFragment con un valore di esempio
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Crea oggetto colore dal canale alfa
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// Imposta le informazioni sul colore per l'istanza di testo
text.TextState.ForegroundColor = color;
// Aggiungi testo alla raccolta di paragrafi dell'istanza di pagina
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Conclusione
Hai aggiunto con successo testo trasparente al tuo documento PDF utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è il focus di questo tutorial?

R: Questo tutorial si concentra sull'aggiunta di testo trasparente a un documento PDF utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari per ottenere questo effetto.

#### D: Quali spazi dei nomi devono essere importati per questo tutorial?

R: Nel file di codice in cui desideri aggiungere testo trasparente, importa i seguenti spazi dei nomi all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### D: Come posso specificare la directory dei documenti?

 A: Nel codice, trova la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso creare una nuova istanza del documento?

 R: Nel passaggio 4 creerai un'istanza di new`Document` oggetto utilizzando il codice fornito.

#### D: Come faccio ad aggiungere una pagina al documento?

 R: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione.

#### D: Come posso creare un oggetto Graph?

 R: Nel passaggio 6 ne creerai uno nuovo`Graph` oggetto con una larghezza e un'altezza specifiche.

#### D: Come posso creare un rettangolo con trasparenza?

R: Nel passaggio 7, creerai un rettangolo con dimensioni specifiche e imposterai il suo colore di riempimento su un colore trasparente utilizzando il`Color.FromRgb` metodo.

#### D: Come aggiungo l'oggetto Graph alla pagina?

 R: Nel passaggio 8 aggiungerai il file`Graph` opporsi alla raccolta di paragrafi della pagina.

#### D: Come imposto la posizione dell'oggetto Graph?

 R: Al punto 9, imposterai il`IsChangePosition` proprietà del`Graph` opporsi a`false` per evitare che cambi posizione.

#### D: Come posso creare un TextFragment con trasparenza?

 R: Nel passaggio 10 creerai un file`TextFragment` oggetto e impostarne il contenuto e`ForegroundColor` proprietà per ottenere un testo trasparente.

#### D: Come posso salvare il documento PDF?

 R: Nel passaggio 11, salverai il documento PDF utilizzando il file`Save` metodo del`Document` oggetto.

#### D: Qual è il punto principale di questo tutorial?

R: Seguendo questo tutorial, hai imparato come aggiungere testo trasparente a un documento PDF utilizzando Aspose.PDF per .NET. Questo può essere utile per creare documenti PDF visivamente accattivanti e creativi.