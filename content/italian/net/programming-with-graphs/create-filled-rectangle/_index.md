---
title: Crea rettangolo pieno
linktitle: Crea rettangolo pieno
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come creare un rettangolo riempito con Aspose.PDF per .NET. Guida passo passo per personalizzare il colore di riempimento.
type: docs
weight: 50
url: /it/net/programming-with-graphs/create-filled-rectangle/
---
In questo tutorial, ti guideremo passo dopo passo attraverso il seguente codice sorgente C# per creare un rettangolo riempito utilizzando Aspose.PDF per .NET.

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

## Passaggio 4: crea un oggetto rettangolo e aggiungi al grafico

Creiamo un oggetto Rettangolo con le dimensioni specificate e lo aggiungiamo alla raccolta di forme del grafico.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Passaggio 5: impostazione del colore di riempimento

Possiamo specificare il colore di riempimento del rettangolo utilizzando la proprietà FillColor dell'oggetto GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Passaggio 6: salvataggio del file PDF risultante

Infine, salviamo il file PDF risultante con il nome "CreateFilledRectangle_out.pdf" nella directory specificata.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Codice sorgente di esempio per Crea rettangolo riempito utilizzando Aspose.PDF per .NET 

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
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Specificare il colore di riempimento per l'oggetto grafico
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Aggiungi un oggetto rettangolo alla raccolta di forme dell'oggetto grafico
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Salva file PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Conclusione

In questo tutorial, abbiamo spiegato come creare un rettangolo riempito utilizzando Aspose.PDF per .NET. Ora puoi utilizzare queste conoscenze per creare forme geometriche con colori di riempimento personalizzati nei tuoi file PDF.

## Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

R: Lo scopo di questo tutorial è guidarti attraverso il processo di creazione di un rettangolo riempito utilizzando Aspose.PDF per .NET, consentendoti di aggiungere forme geometriche personalizzate con colori di riempimento ai tuoi file PDF.

#### D: Quali prerequisiti sono richiesti prima di iniziare?

R: Prima di iniziare, assicurati di aver installato la libreria Aspose.PDF e di aver configurato il tuo ambiente di sviluppo. Inoltre, si consiglia di avere una conoscenza di base della programmazione C#.

#### D: Come posso specificare la directory in cui salvare il file PDF?

R: Nel codice sorgente fornito, puoi modificare la variabile "dataDir" per indicare la directory in cui desideri salvare il file PDF risultante.

#### D: Qual è lo scopo dell'oggetto Graph?

R: L'oggetto Graph funge da contenitore per gli elementi di disegno. Viene creato con le dimensioni specificate e aggiunto alla raccolta di paragrafi della pagina.

#### D: Come posso aggiungere un rettangolo pieno al documento PDF?

R: Per aggiungere un rettangolo riempito, crea un'istanza della classe Rectangle con le dimensioni e il colore di riempimento specificati e aggiungila alla raccolta di forme del grafico.

#### D: Posso personalizzare le dimensioni e il colore di riempimento del rettangolo?

 R: Sì, puoi personalizzare le dimensioni e il colore di riempimento del rettangolo modificando i parametri passati al`Aspose.Pdf.Drawing.Rectangle` costruttore e impostando la proprietà FillColor.

#### D: Come posso salvare il file PDF risultante dopo aver creato il rettangolo riempito?

 R: Dopo aver creato il rettangolo riempito, puoi salvare il file PDF risultante utilizzando il file`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` riga nel codice sorgente fornito.