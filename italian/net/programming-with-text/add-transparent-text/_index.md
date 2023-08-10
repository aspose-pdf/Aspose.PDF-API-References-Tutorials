---
title: Aggiungi testo trasparente
linktitle: Aggiungi testo trasparente
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere testo trasparente a un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-text/add-transparent-text/
---

Questo tutorial ti guiderà attraverso il processo di aggiunta di testo trasparente a un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di disporre di quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato nel tuo computer.
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

## Passaggio 3: impostare la directory dei documenti
 Nel codice, individuare la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i documenti.

## Passaggio 4: creare una nuova istanza del documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione. Nel codice fornito, la nuova pagina è assegnata alla variabile`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Passaggio 6: creare un oggetto grafico
 Crea un nuovo`Graph` oggetto con larghezza e altezza specifiche.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Passaggio 7: crea un rettangolo con trasparenza
 Crea un rettangolo con dimensioni specifiche e imposta il suo colore di riempimento su un colore trasparente utilizzando il`Color.FromRgb` metodo.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Passaggio 8: aggiungere l'oggetto Graph alla pagina
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

### Esempio di codice sorgente per Aggiungi testo trasparente utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza di documento
Document doc = new Document();
// Crea una raccolta da pagina a pagina di file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Crea oggetto grafico
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Crea un'istanza rettangolare con determinate dimensioni
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Crea un oggetto colore dal canale di colore alfa
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Aggiungi rectanlge alla raccolta di forme dell'oggetto Graph
canvas.Shapes.Add(rect);
// Aggiungi oggetto grafico alla raccolta di paragrafi dell'oggetto pagina
page.Paragraphs.Add(canvas);
// Imposta il valore per non modificare la posizione dell'oggetto grafico
canvas.IsChangePosition = false;
// Crea un'istanza TextFragment con un valore di esempio
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Crea un oggetto colore dal canale alfa
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