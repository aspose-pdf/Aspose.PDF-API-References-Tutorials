---
title: Crea un rettangolo con colore alfa
linktitle: Crea un rettangolo con colore alfa
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come creare un rettangolo con colore trasparente utilizzando Aspose.PDF per .NET. Guida passo passo per personalizzare la trasparenza.
type: docs
weight: 60
url: /it/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
In questo tutorial ti guideremo passo dopo passo attraverso il seguente codice sorgente C# per creare un rettangolo con colore alfa utilizzando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di aver impostato il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

## Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, devi specificare la directory in cui vuoi salvare il file PDF risultante. Cambia la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione di un oggetto documento e aggiunta di una pagina

Creiamo un'istanza della classe Document e aggiungiamo una pagina a questo documento.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Passaggio 3: creazione di un oggetto grafico e di un rettangolo

Creiamo un oggetto Graph con dimensioni specificate e un rettangolo con dimensioni specificate.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Passaggio 4: impostazione del colore alfa per il rettangolo

Possiamo specificare un colore alfa per il rettangolo utilizzando il metodo FromArgb della classe System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Passaggio 5: aggiunta del rettangolo all'oggetto grafico

Aggiungiamo il rettangolo alla raccolta di forme dell'oggetto Graph.

```csharp
canvas.Shapes.Add(rect);
```

## Passaggio 6: creazione di un secondo rettangolo con un colore alfa diverso

Creiamo un secondo rettangolo con dimensioni specifiche e un altro colore alfa.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Passaggio 7: aggiunta dell'oggetto grafico alla pagina

Aggiungiamo l'oggetto Graph alla raccolta Paragraph dell'oggetto Page.

```csharp
page.Paragraphs.Add(canvas);
```

## Passaggio 8: salvataggio del file PDF risultante

Infine, salviamo il file PDF risultante con il nome "CreateRectangleWithAlphaColor_out.pdf" nella directory specificata.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Esempio di codice sorgente per creare un rettangolo con colore alfa utilizzando Aspose.PDF per .NET 

```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza del documento
Document doc = new Document();
// Aggiungi pagina alla raccolta di pagine del file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Crea istanza del grafico
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Crea un oggetto rettangolare con dimensioni specifiche
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Imposta il colore di riempimento del grafico dalla struttura System.Drawing.Color da un valore ARGB a 32 bit
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Aggiungi oggetto rettangolo alla raccolta di forme dell'istanza Graph
canvas.Shapes.Add(rect);
// Crea un secondo oggetto rettangolare
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Aggiungere un'istanza di grafico alla raccolta di paragrafi dell'oggetto pagina
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Salva file PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Conclusione

In questo tutorial, abbiamo spiegato come creare un rettangolo con colore alfa usando Aspose.PDF per .NET. Ora puoi usare questa conoscenza per creare forme geometriche con colori trasparenti nei tuoi file PDF.

## Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

R: Questo tutorial ha lo scopo di guidarti attraverso il processo di creazione di un rettangolo con colore alfa usando Aspose.PDF per .NET. Imparerai come aggiungere forme geometriche con colori trasparenti ai tuoi file PDF.

#### D: Quali prerequisiti sono richiesti prima di iniziare?

R: Prima di iniziare, assicurati di aver installato la libreria Aspose.PDF e di aver impostato il tuo ambiente di sviluppo. Inoltre, è consigliabile avere una conoscenza di base della programmazione C#.

#### D: Come faccio a specificare la directory in cui salvare il file PDF?

R: Nel codice sorgente fornito, è possibile modificare la variabile "dataDir" per indicare la directory in cui si desidera salvare il file PDF risultante.

#### D: Qual è lo scopo degli oggetti Grafico e Rettangolo?

R: L'oggetto Graph funge da contenitore per gli elementi di disegno, mentre Rectangle rappresenta la forma geometrica che aggiungerai al PDF.

#### D: Come posso impostare un colore alfa per il rettangolo?

 A: È possibile specificare un colore alfa per il rettangolo utilizzando`FillColor` proprietà del`GraphInfo` oggetto e il`Color.FromRgb` metodo con un valore ARGB.

#### D: Posso creare più rettangoli con colori alfa diversi?

R: Sì, puoi creare più rettangoli con diversi colori alfa seguendo passaggi simili a quelli illustrati nel tutorial.

#### D: Come posso salvare il file PDF risultante dopo aver creato i rettangoli con colori alfa?

 A: Dopo aver creato i rettangoli con i colori alfa, puoi salvare il file PDF risultante utilizzando`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` riga nel codice sorgente fornito.