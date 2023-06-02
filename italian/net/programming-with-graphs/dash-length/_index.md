---
title: Lunghezza trattino
linktitle: Lunghezza trattino
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come impostare la lunghezza dei trattini con Aspose.PDF per .NET. Guida passo passo per personalizzare i modelli di trattino.
type: docs
weight: 70
url: /it/net/programming-with-graphs/dash-length/
---
In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per impostare la lunghezza dei trattini usando Aspose.PDF per .NET.

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
Page page = doc.Pages.Add();
```

## Passaggio 3: creazione di un oggetto grafico e aggiunta alla pagina

Creiamo un oggetto Graph con dimensioni specificate e lo aggiungiamo alla raccolta di paragrafi della pagina.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Passaggio 4: creazione di un oggetto linea e configurazione

Creiamo un oggetto Line con le coordinate specificate e configuriamo il colore e la lunghezza dei trattini.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Passaggio 5: aggiunta della linea all'oggetto grafico

Aggiungiamo la linea alla raccolta di forme dell'oggetto Graph.

```csharp
canvas.Shapes.Add(line);
```

## Passaggio 6: salvataggio del file PDF risultante

Infine, salviamo il file PDF risultante con il nome "DashLength_out.pdf" nella directory specificata.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Esempio di codice sorgente per Dash Length utilizzando Aspose.Words per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Istanza documento istanza
Document doc = new Document();
// Aggiungi la pagina alla raccolta di pagine dell'oggetto Document
Page page = doc.Pages.Add();
// Crea un oggetto di disegno con determinate dimensioni
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Aggiungi oggetto di disegno alla raccolta di paragrafi dell'istanza di pagina
page.Paragraphs.Add(canvas);
// Crea oggetto Linea
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Imposta il colore per l'oggetto Linea
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Specifica la matrice di trattini per l'oggetto linea
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Imposta la fase del trattino per l'istanza della linea
line.GraphInfo.DashPhase = 1;
// Aggiungi una linea alla raccolta di forme dell'oggetto di disegno
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Salva documento PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Conclusione

In questo tutorial, abbiamo spiegato come impostare la lunghezza dei trattini utilizzando Aspose.PDF per .NET. Ora puoi usare questa conoscenza per creare linee con trattini personalizzati nei tuoi file PDF.
