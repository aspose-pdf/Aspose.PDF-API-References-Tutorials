---
title: Aggiungi oggetto linea nel file PDF
linktitle: Aggiungi oggetto linea nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere un oggetto linea personalizzato in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-graphs/add-line-object/
---
In questo tutorial, ti guideremo passo dopo passo attraverso il seguente codice sorgente C# per aggiungere un oggetto riga utilizzando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di configurare il tuo ambiente di sviluppo prima di iniziare. Possiede inoltre una conoscenza base della programmazione C#.

## Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, devi specificare la directory in cui desideri salvare il file PDF risultante. Modificare la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione di un'istanza del documento e aggiunta di una pagina

Creiamo un'istanza della classe Document e aggiungiamo una pagina a questo documento.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Passaggio 3: creazione di un oggetto grafico e aggiunta alla pagina

Creiamo un oggetto Graph con le dimensioni specificate e lo aggiungiamo alla raccolta di paragrafi della pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Passaggio 4: crea un oggetto linea e aggiungi al grafico

Creiamo un oggetto Linea con le coordinate specificate e lo aggiungiamo alla raccolta di forme del grafico.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Passaggio 5: impostazione della linea

Possiamo specificare le proprietà della linea, come il tipo di trattino e la fase del trattino.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Passaggio 6: salvataggio del file PDF

Infine, salviamo il file PDF risultante con il nome "AddLineObject_out.pdf" nella directory specificata.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Codice sorgente di esempio per Aggiungi oggetto riga utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea istanza del documento
Document doc = new Document();
// Aggiungi una raccolta di pagine a pagine di file PDF
Page page = doc.Pages.Add();
// Crea un'istanza del grafico
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Aggiungi un oggetto grafico alla raccolta di paragrafi dell'istanza di pagina
page.Paragraphs.Add(graph);
// Crea un'istanza Rectangle
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Specificare il colore di riempimento per l'oggetto grafico
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Aggiungi un oggetto rettangolo alla raccolta di forme dell'oggetto grafico
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Salva file PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Conclusione

In questo tutorial, abbiamo spiegato passo dopo passo come aggiungere un oggetto linea utilizzando Aspose.PDF per .NET. Ora puoi utilizzare questa conoscenza per creare documenti PDF con righe personalizzate nelle tue applicazioni.

### Domande frequenti sull'aggiunta di oggetti riga nel file PDF

#### D: Qual è lo scopo di questo tutorial?

R: Questo tutorial ha lo scopo di guidarti attraverso il processo di aggiunta di un oggetto linea utilizzando Aspose.PDF per .NET per migliorare i tuoi documenti PDF.

#### D: Quali prerequisiti sono richiesti prima di iniziare?

R: Prima di iniziare, assicurati di aver installato la libreria Aspose.PDF e di aver configurato il tuo ambiente di sviluppo. Inoltre, si consiglia di avere una conoscenza di base della programmazione C#.

#### D: Come posso specificare la directory in cui salvare il file PDF?

R: Nel codice sorgente fornito, puoi modificare la variabile "dataDir" per indicare la directory in cui desideri salvare il file PDF risultante.

#### D: Qual è lo scopo dell'oggetto Graph?

R: L'oggetto Graph funge da contenitore per gli elementi di disegno. Viene creato con le dimensioni specificate e aggiunto alla raccolta di paragrafi della pagina.

#### D: Come posso aggiungere un oggetto linea al documento PDF?

R: Per aggiungere un oggetto linea, crea un'istanza della classe Linea con le coordinate specificate e aggiungila alla raccolta di forme del grafico.

#### D: Posso personalizzare l'aspetto della linea?

R: Sì, puoi personalizzare l'aspetto della linea impostando proprietà come il tipo e la fase del trattino utilizzando la proprietà GraphInfo dell'oggetto Line.

#### D: Qual è lo scopo di specificare il dash array e la fase del dash?

R: Le proprietà Dash Array e Dash Phase ti consentono di creare linee tratteggiate o punteggiate con motivi specifici.

#### D: Come posso salvare il file PDF dopo aver aggiunto l'oggetto linea?

 R: Dopo aver aggiunto l'oggetto linea, puoi salvare il file PDF risultante utilizzando il file`doc.Save(dataDir + "AddLineObject_out.pdf");` riga nel codice sorgente fornito.

#### D: È disponibile un codice sorgente di esempio?

R: Sì, il tutorial include un codice sorgente di esempio a cui puoi fare riferimento per implementare i passaggi descritti.