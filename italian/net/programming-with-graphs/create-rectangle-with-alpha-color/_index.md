---
title: Crea rettangolo con colore alfa
linktitle: Crea rettangolo con colore alfa
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come creare un rettangolo con colore trasparente utilizzando Aspose.PDF per .NET. Guida passo passo per personalizzare la trasparenza.
type: docs
weight: 60
url: /it/net/programming-with-graphs/create-rectangle-with-alpha-color/
---

In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per creare un rettangolo con colore alfa usando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di configurare il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

## Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, è necessario specificare la directory in cui si desidera salvare il file PDF risultante. Modificare la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione di un'istanza di un oggetto documento e aggiunta di una pagina

Creiamo un'istanza della classe Document e aggiungiamo una pagina a questo documento.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Passaggio 3: creazione di un oggetto grafico e di un rettangolo

Creiamo un oggetto Graph con dimensioni specificate e un rettangolo con dimensioni specifiche.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Passaggio 4: impostazione del colore alfa per il rettangolo

Possiamo specificare un colore alfa per il rettangolo usando il metodo FromArgb della classe System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Passaggio 5: aggiunta del rettangolo all'oggetto grafico

Aggiungiamo il rettangolo alla raccolta di forme dell'oggetto Graph.

```csharp
canvas.Shapes.Add(rect);
```

## Passaggio 6: creazione di un secondo rettangolo con un diverso colore alfa

Creiamo un secondo rettangolo con dimensioni specifiche e un altro colore alfa.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Passaggio 7: aggiunta dell'oggetto grafico alla pagina

Aggiungiamo l'oggetto Graph alla collezione Paragraph dell'oggetto Page.

```csharp
page.Paragraphs.Add(canvas);
```

## Passaggio 8: salvataggio del file PDF risultante

Infine, salviamo il file PDF risultante con il nome "CreateRectangleWithAlphaColor_out.pdf" nella directory specificata.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Esempio di codice sorgente per Crea rettangolo con colore alfa utilizzando Aspose.Words per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Istanza documento istanza
Document doc = new Document();
// Aggiungi pagine alla raccolta di pagine di file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Crea istanza Graph
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Crea un oggetto rettangolo con dimensioni specifiche
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Imposta il colore di riempimento del grafico dalla struttura System.Drawing.Color da un valore ARGB a 32 bit
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Aggiungi un oggetto rettangolo alla raccolta di forme dell'istanza Graph
canvas.Shapes.Add(rect);
// Crea il secondo oggetto rettangolo
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Aggiungi un'istanza di grafico alla raccolta di paragrafi dell'oggetto pagina
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Salva file PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Conclusione

In questo tutorial, abbiamo spiegato come creare un rettangolo con colore alfa utilizzando Aspose.PDF per .NET. Ora puoi usare questa conoscenza per creare forme geometriche con colori trasparenti nei tuoi file PDF.
