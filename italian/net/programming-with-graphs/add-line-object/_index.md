---
title: Aggiungi oggetto linea
linktitle: Aggiungi oggetto linea
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere un oggetto linea personalizzato in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-graphs/add-line-object/
---
In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per aggiungere un oggetto linea usando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di configurare il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

## Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, è necessario specificare la directory in cui si desidera salvare il file PDF risultante. Modificare la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione di un'istanza di documento e aggiunta di una pagina

Creiamo un'istanza della classe Document e aggiungiamo una pagina a questo documento.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Passaggio 3: creazione di un oggetto grafico e aggiunta alla pagina

Creiamo un oggetto Graph con dimensioni specificate e lo aggiungiamo alla raccolta di paragrafi della pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Passaggio 4: crea un oggetto linea e aggiungi al grafico

Creiamo un oggetto Line con le coordinate specificate e lo aggiungiamo alla raccolta di forme del grafico.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Passaggio 5: configurazione della linea

Possiamo specificare le proprietà per la linea, come il tipo di trattino e la fase di trattino.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Passaggio 6: salvare il file PDF

Infine, salviamo il file PDF risultante con il nome "AddLineObject_out.pdf" nella directory specificata.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Esempio di codice sorgente per Aggiungi oggetto linea utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza di documento
Document doc = new Document();
// Aggiungi pagine alla raccolta di pagine di file PDF
Page page = doc.Pages.Add();
// Crea istanza Graph
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Aggiungi oggetto grafico alla raccolta di paragrafi dell'istanza di pagina
page.Paragraphs.Add(graph);
// Crea un'istanza Rectangle
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Specificare il colore di riempimento per l'oggetto grafico
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Aggiungi l'oggetto rettangolo alla raccolta di forme dell'oggetto grafico
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Salva file PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Conclusione

In questo tutorial, abbiamo spiegato passo dopo passo come aggiungere un oggetto linea utilizzando Aspose.PDF per .NET. Ora puoi utilizzare questa conoscenza per creare documenti PDF con linee personalizzate nelle tue applicazioni.
