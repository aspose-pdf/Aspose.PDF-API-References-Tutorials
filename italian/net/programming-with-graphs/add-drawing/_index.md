---
title: Aggiungi disegno
linktitle: Aggiungi disegno
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere disegni utilizzando Aspose.PDF per .NET. Segui questa guida passo passo per creare interessanti documenti PDF con funzionalità di disegno.
type: docs
weight: 10
url: /it/net/programming-with-graphs/add-drawing/
---

Lo sviluppo di applicazioni richiede spesso l'aggiunta di funzionalità come disegni e grafica per rendere i documenti più attraenti e informativi. In questo articolo, ti guideremo passo dopo passo per spiegare il codice sorgente C# per aggiungere il disegno alla programmazione con la grafica usando Aspose.PDF per .NET.

Prima di iniziare, assicurati di aver installato la libreria Aspose.PDF e configurato il tuo ambiente di sviluppo. Inoltre, assicurati di avere una conoscenza di base della programmazione C#.

## Passaggio 1: Introduzione a Aspose.PDF per .NET e alle sue funzionalità

Aspose.PDF è una libreria potente e versatile per creare, manipolare e convertire file PDF in applicazioni .NET. Offre una vasta gamma di funzionalità per lavorare con documenti PDF, inclusa l'aggiunta di disegni, grafica, testo, ecc.

## Passaggio 2: comprendere il codice sorgente per aggiungere disegni utilizzando Aspose.PDF

Il codice sorgente fornito utilizza la libreria Aspose.PDF per creare un semplice disegno in un documento PDF. Ora esamineremo in dettaglio ogni passaggio del codice.

## Passaggio 3: configurazione della directory dei documenti e inizializzazione delle variabili

Nel codice sorgente, è necessario specificare la directory in cui si desidera salvare il file PDF risultante. È possibile modificare la variabile "dataDir" per indicare la directory desiderata.

Inoltre, il codice inizializza le variabili per i componenti di colore alfa, rosso, verde e blu.

## Passaggio 4: creazione di un oggetto colore con Alpha RGB

La seguente riga di codice crea un oggetto Color utilizzando i valori alfa, rosso, verde e blu specificati:

```csharp
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue);
```

Ciò consente di definire un colore con un canale alfa, il che significa che il colore può essere parzialmente trasparente.

## Passaggio 5: creazione di un'istanza di un oggetto documento

Per iniziare a lavorare con Aspose.PDF, dobbiamo creare un'istanza della classe Document. Questo rappresenta il nostro documento PDF.

```csharp
Document document = new Document();
```

## Passaggio 6: aggiunta di una pagina al file PDF

Dobbiamo aggiungere una pagina al file PDF in cui vogliamo visualizzare il nostro disegno.

```csharp
Page page = document.Pages.Add();
```

## Passaggio 7: creazione di un oggetto grafico con dimensioni

In questo passaggio creiamo un oggetto Graph con le dimensioni specificate. Questo oggetto servirà da contenitore per il nostro disegno.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
```

## Passaggio 8: impostazione del bordo per l'oggetto Disegno

Possiamo impostare il bordo dell'oggetto Drawing utilizzando la classe BorderInfo.

```csharp
graph.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black);
```

Questo imposterà un bordo nero attorno al nostro disegno.

## Passaggio 9: aggiunta dell'oggetto grafico alla pagina

Ora aggiungiamo l'oggetto grafico alla raccolta dei paragrafi dell'istanza della classe Page.

```csharp
page.Paragraphs.Add(graph);
```

## Passaggio 10: creazione di un oggetto rettangolo con dimensioni

Creiamo un oggetto Rectangle con le dimensioni specificate. Questo rettangolo verrà aggiunto al nostro disegno.

```csharp
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
```

## Passaggio 11: creazione di un oggetto GraphInfo per l'istanza Rectangle

Abbiamo bisogno di creare un oggetto GraphInfo per l'istanza Rectangle per configurare le sue proprietà del grafico.

```csharp
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
```

## Passaggio 12: configurazione delle informazioni sul colore per l'oggetto GraphInfo

Possiamo configurare le informazioni sul colore per l'oggetto GraphInfo utilizzando le proprietà Color e FillColor.

```csharp
graphInfo.Color = Aspose.Pdf.Color.Red;
graphInfo. FillColor = alphaColor;
```

Questo imposterà il colore del bordo del rettangolo su rosso e il colore di riempimento sul colore alfa specificato.

## Passaggio 13: aggiunta della forma rettangolare all'oggetto grafico

Ora aggiungiamo la forma del rettangolo alla raccolta di forme dell'oggetto grafico.

```csharp
graph.Shapes.Add(rectangle);
```
## Passaggio 14: salva il file PDF e visualizza il messaggio di successo

Infine, salviamo il file PDF e visualizziamo un messaggio che indica che il disegno è stato aggiunto correttamente.

```csharp
dataDir = dataDir + "AddDrawing_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nSuccessfully added drawing with transparent color.\nFile saved to location: " + dataDir);
```

### Esempio di codice sorgente per Aggiungi disegno utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
// Crea un oggetto Color usando Alpha RGB
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue); // Fornire canale alfa
// Crea un'istanza dell'oggetto Document
Document document = new Document();
// Aggiungi pagine alla raccolta di pagine di file PDF
Page page = document.Pages.Add();
// Crea un oggetto grafico con determinate dimensioni
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
// Imposta il bordo per l'oggetto di disegno
graph.Border = (new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black));
// Aggiungi un oggetto grafico alla raccolta di paragrafi dell'istanza di Page
page.Paragraphs.Add(graph);
// Crea un oggetto Rettangolo con determinate dimensioni
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
// Crea un oggetto graphInfo per l'istanza Rectangle
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
// Imposta le informazioni sul colore per l'istanza GraphInfo
graphInfo.Color = (Aspose.Pdf.Color.Red);
// Imposta il colore di riempimento per GraphInfo
graphInfo.FillColor = (alphaColor);
// Aggiungi la forma rettangolare alla raccolta di forme dell'oggetto grafico
graph.Shapes.Add(rectangle);
dataDir = dataDir + "AddDrawing_out.pdf";
// Salva file PDF
document.Save(dataDir);
Console.WriteLine("\nDrawing added successfully with transparent color.\nFile saved at " + dataDir);            

```

## Conclusione

In questo articolo, abbiamo imparato come aggiungere il disegno alla programmazione con la grafica utilizzando Aspose.PDF per .NET. Abbiamo seguito una guida passo passo per comprendere il codice sorgente e i vari passaggi necessari per aggiungere un disegno a un file PDF. Utilizzando le potenti funzionalità di Aspose.PDF, puoi creare documenti PDF attraenti e interattivi nelle tue applicazioni .NET.