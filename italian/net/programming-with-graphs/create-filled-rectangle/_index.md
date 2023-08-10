---
title: Crea rettangolo pieno
linktitle: Crea rettangolo pieno
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come creare un rettangolo pieno con Aspose.PDF per .NET. Guida passo passo per personalizzare il colore di riempimento.
type: docs
weight: 50
url: /it/net/programming-with-graphs/create-filled-rectangle/
---
In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per creare un rettangolo pieno usando Aspose.PDF per .NET.

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

## Passaggio 4: crea un oggetto rettangolo e aggiungi al grafico

Creiamo un oggetto Rectangle con le dimensioni specificate e lo aggiungiamo alla raccolta di forme del grafico.

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

### Esempio di codice sorgente per Crea rettangolo pieno utilizzando Aspose.PDF per .NET 

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
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Specificare il colore di riempimento per l'oggetto grafico
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Aggiungi l'oggetto rettangolo alla raccolta di forme dell'oggetto grafico
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Salva file PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Conclusione

In questo tutorial, abbiamo spiegato come creare un rettangolo pieno usando Aspose.PDF per .NET. Ora puoi usare questa conoscenza per creare forme geometriche con colori di riempimento personalizzati nei tuoi file PDF.

## FAQ

#### D: Qual è lo scopo di questo tutorial?

R: Lo scopo di questo tutorial è guidarti attraverso il processo di creazione di un rettangolo pieno utilizzando Aspose.PDF per .NET, consentendoti di aggiungere forme geometriche personalizzate con colori di riempimento ai tuoi file PDF.

#### D: Quali prerequisiti sono richiesti prima di iniziare?

A: Prima di iniziare, assicurati di aver installato la libreria Aspose.PDF e di aver impostato il tuo ambiente di sviluppo. Inoltre, è consigliabile avere una conoscenza di base della programmazione C#.

#### D: Come faccio a specificare la directory per salvare il file PDF?

R: Nel codice sorgente fornito, è possibile modificare la variabile "dataDir" per indicare la directory in cui si desidera salvare il file PDF risultante.

#### D: Qual è lo scopo dell'oggetto Graph?

R: L'oggetto Graph funge da contenitore per gli elementi di disegno. Viene creato con dimensioni specificate e aggiunto alla raccolta di paragrafi della pagina.

#### D: Come posso aggiungere un rettangolo pieno al documento PDF?

R: Per aggiungere un rettangolo pieno, crea un'istanza della classe Rectangle con dimensioni e colore di riempimento specificati e aggiungila alla raccolta di forme del grafico.

#### D: Posso personalizzare le dimensioni e il colore di riempimento del rettangolo?

 R: Sì, puoi personalizzare le dimensioni e il colore di riempimento del rettangolo modificando i parametri passati al`Aspose.Pdf.Drawing.Rectangle` costruttore e impostando la proprietà FillColor.

#### D: Come faccio a salvare il file PDF risultante dopo aver creato il rettangolo pieno?

 R: Dopo aver creato il rettangolo pieno, puoi salvare il file PDF risultante utilizzando il file`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` riga nel codice sorgente fornito.