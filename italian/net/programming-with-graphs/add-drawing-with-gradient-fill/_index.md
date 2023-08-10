---
title: Aggiungi disegno con riempimento sfumato
linktitle: Aggiungi disegno con riempimento sfumato
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere un disegno con riempimento sfumato con Aspose.PDF per .NET. Tutorial passo dopo passo per creare interessanti documenti PDF.
type: docs
weight: 20
url: /it/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per aggiungere un disegno con riempimento sfumato alla programmazione con grafica utilizzando Aspose.PDF per .NET.

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
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Passaggio 4: crea un oggetto rettangolo e aggiungi al grafico

Creiamo un oggetto Rectangle con dimensioni specificate e lo aggiungiamo alla raccolta di forme del grafico.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Passaggio 5: configurazione del riempimento sfumato

Configuriamo il riempimento sfumato per il rettangolo usando la classe GradientAxialShading.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

Questo crea un riempimento sfumato dal rosso al blu, dal punto (0, 0) al punto (300, 300).

## Passaggio 6: salvare il file PDF

Infine, salviamo il file PDF risultante con il nome "AddDrawingWithGradientFill_out.pdf" nella directory specificata.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Esempio di codice sorgente per Aggiungi disegno con riempimento sfumato utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Conclusione

In questo tutorial, abbiamo spiegato passo dopo passo come aggiungere un disegno con un riempimento sfumato alla programmazione con la grafica utilizzando Aspose.PDF per .NET. Ora puoi utilizzare questa conoscenza per creare interessanti documenti PDF con design personalizzati e riempimenti sfumati.

### FAQ

#### D: Qual è lo scopo di questo tutorial?

A: Questo tutorial ha lo scopo di guidarti attraverso il processo di aggiunta di un disegno con riempimento sfumato alla programmazione con grafica utilizzando Aspose.PDF per .NET.

#### D: Quali prerequisiti sono richiesti prima di iniziare?

A: Prima di iniziare, assicurati di aver installato la libreria Aspose.PDF e di aver impostato il tuo ambiente di sviluppo. Inoltre, è consigliabile avere una conoscenza di base della programmazione C#.

#### D: Come faccio a specificare la directory per salvare il file PDF?

R: Nel codice sorgente fornito, è possibile modificare il valore della variabile "dataDir" per indicare la directory in cui si desidera salvare il file PDF risultante.

#### D: Qual è lo scopo dell'oggetto Graph?

R: L'oggetto Graph funge da contenitore per gli elementi del disegno. Viene creato con dimensioni specificate e aggiunto alla raccolta di paragrafi della pagina.

#### D: Come posso configurare il riempimento sfumato per una forma?

R: Per configurare il riempimento sfumato, puoi impostare la proprietà FillColor di GraphInfo di una forma utilizzando la classe GradientAxialShading. Ciò consente di definire i punti iniziale e finale del gradiente e i colori tra cui passare.

#### D: Posso personalizzare i colori e la direzione del riempimento sfumato?

R: Sì, puoi personalizzare i colori e la direzione del riempimento sfumato regolando gli oggetti Color e specificando i punti iniziale e finale di GradientAxialShading.

#### D: Qual è il passaggio finale del tutorial?

R: Il passaggio finale prevede il salvataggio del file PDF risultante con il nome "AddDrawingWithGradientFill_out.pdf" nella directory specificata.

#### D: È disponibile un codice sorgente di esempio?

R: Sì, il tutorial fornisce un codice sorgente di esempio che puoi utilizzare come riferimento per implementare i passaggi descritti.

#### D: Posso applicare il riempimento sfumato ad altre forme oltre ai rettangoli?

R: Sì, puoi applicare il riempimento sfumato anche ad altre forme. Il processo prevede la configurazione della proprietà FillColor del GraphInfo della forma utilizzando la classe GradientAxialShading.