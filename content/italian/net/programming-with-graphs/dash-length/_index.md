---
title: Lunghezza del trattino
linktitle: Lunghezza del trattino
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come impostare la lunghezza dei trattini con Aspose.PDF per .NET. Guida passo passo per personalizzare i modelli di trattini.
type: docs
weight: 70
url: /it/net/programming-with-graphs/dash-length/
---
In questo tutorial ti guideremo passo dopo passo attraverso il seguente codice sorgente C# per impostare la lunghezza dei trattini utilizzando Aspose.PDF per .NET.

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

### Esempio di codice sorgente per Dash Length utilizzando Aspose.PDF per .NET 

```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza del documento
Document doc = new Document();
// Aggiungi pagina alla raccolta di pagine dell'oggetto Documento
Page page = doc.Pages.Add();
// Crea un oggetto Disegno con determinate dimensioni
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Aggiungi oggetto di disegno alla raccolta di paragrafi dell'istanza di pagina
page.Paragraphs.Add(canvas);
// Crea oggetto Linea
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Imposta il colore per l'oggetto Linea
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Specificare la matrice di trattini per l'oggetto linea
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

In questo tutorial, abbiamo spiegato come impostare la lunghezza dei trattini usando Aspose.PDF per .NET. Ora puoi usare questa conoscenza per creare linee con modelli di trattini personalizzati nei tuoi file PDF.

## Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

R: Lo scopo di questo tutorial è guidarti attraverso il processo di impostazione della lunghezza dei trattini per le linee usando Aspose.PDF per .NET. Imparerai come creare linee con modelli di trattini personalizzati nei tuoi file PDF.

#### D: Quali prerequisiti sono richiesti prima di iniziare?

R: Prima di iniziare, assicurati di aver installato la libreria Aspose.PDF e di aver impostato il tuo ambiente di sviluppo. Si consiglia anche una conoscenza di base della programmazione C#.

#### D: Come faccio a specificare la directory in cui salvare il file PDF?

A: Modificare la variabile "dataDir" nel codice sorgente fornito per indicare la directory in cui si desidera salvare il file PDF risultante.

#### D: Come posso creare una linea con motivi di tratteggio personalizzati?

 A: Il tutorial illustra la creazione di un oggetto Linea e la configurazione del suo colore, della matrice di trattini e della fase di trattino utilizzando`GraphInfo` oggetto. Modificare queste impostazioni per ottenere il modello di tratteggio desiderato.

#### D: Posso personalizzare il colore della linea?

 A: Sì, puoi personalizzare il colore della linea impostando`Color` proprietà del`GraphInfo` oggetto associato alla Linea.

#### D: Come posso salvare il documento PDF dopo aver impostato la lunghezza del trattino?

 A: Dopo aver configurato l'oggetto Linea con il modello di tratteggio desiderato, è possibile salvare il documento PDF risultante utilizzando`doc.Save(dataDir + "DashLength_out.pdf");` riga nel codice sorgente fornito.