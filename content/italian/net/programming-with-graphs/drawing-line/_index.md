---
title: Disegno della linea
linktitle: Disegno della linea
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come disegnare una linea su una pagina usando Aspose.PDF per .NET. Guida passo passo per creare linee personalizzate.
type: docs
weight: 80
url: /it/net/programming-with-graphs/drawing-line/
---
In questo tutorial ti guideremo passo dopo passo attraverso il seguente codice sorgente C# per disegnare una linea utilizzando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di aver impostato il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

## Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, devi specificare la directory in cui vuoi salvare il file PDF risultante. Cambia la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione di un'istanza di documento e aggiunta di una pagina

Creiamo un'istanza della classe Document e aggiungiamo una pagina a questo documento.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Passaggio 3: impostazione dei margini della pagina

Impostiamo i margini della pagina a 0 su tutti i lati.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Passaggio 4: creazione di un oggetto grafico e della prima linea

Creiamo un oggetto Graph con dimensioni pari a quelle della pagina e tracciamo la prima linea che va dall'angolo inferiore sinistro all'angolo superiore destro della pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Fase 5: Disegnare la seconda linea

Tracciamo la seconda linea che va dall'angolo in alto a sinistra all'angolo in basso a destra della pagina.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Passaggio 6: aggiunta dell'oggetto grafico alla pagina

Aggiungiamo l'oggetto Graph alla raccolta dei paragrafi della pagina.

```csharp
pg.Paragraphs.Add(graph);
```

## Passaggio 7: salvataggio del file PDF risultante

Infine, salviamo il file PDF risultante con il nome "DrawingLine_out.pdf" nella directory specificata.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Esempio di codice sorgente per Drawing Line utilizzando Aspose.PDF per .NET 

```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea istanza del documento
Document pDoc = new Document();
// Aggiungi pagina alla raccolta di pagine del documento PDF
Page pg = pDoc.Pages.Add();
// Imposta il margine della pagina su tutti i lati come 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Crea un oggetto grafico con larghezza e altezza uguali alle dimensioni della pagina
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Crea l'oggetto della prima riga partendo dall'angolo inferiore sinistro fino all'angolo superiore destro della pagina
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Aggiungi una linea alla raccolta di forme dell'oggetto Graph
graph.Shapes.Add(line);
// Traccia una linea dall'angolo in alto a sinistra della pagina all'angolo in basso a destra della pagina
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Aggiungi una linea alla raccolta di forme dell'oggetto Graph
graph.Shapes.Add(line2);
// Aggiungi l'oggetto grafico alla raccolta di paragrafi della pagina
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Salva file PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Conclusione

In questo tutorial, abbiamo spiegato come disegnare una linea usando Aspose.PDF per .NET. Ora puoi usare questa conoscenza per creare forme geometriche con linee personalizzate nei tuoi file PDF.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

R: Lo scopo di questo tutorial è guidarti attraverso il processo di disegno di linee usando Aspose.PDF per .NET. Imparerai come creare linee su una pagina PDF e personalizzarne l'aspetto.

#### D: Quali prerequisiti sono richiesti prima di iniziare?

R: Prima di iniziare, assicurati di aver installato la libreria Aspose.PDF e di aver impostato il tuo ambiente di sviluppo. Si consiglia anche una conoscenza di base della programmazione C#.

#### D: Come faccio a specificare la directory in cui salvare il file PDF?

A: Modificare la variabile "dataDir" nel codice sorgente fornito per indicare la directory in cui si desidera salvare il file PDF risultante.

#### D: Come posso creare delle linee su una pagina PDF?

R: Il tutorial illustra la creazione di un oggetto Graph con le dimensioni della pagina e la successiva aggiunta di oggetti Line. Modifica le coordinate e le proprietà degli oggetti Line per creare le linee desiderate.

#### D: Posso personalizzare l'aspetto delle linee?

R: Sì, puoi personalizzare l'aspetto delle linee modificando le proprietà degli oggetti Line. Ciò include la modifica delle loro coordinate, colore, spessore e altri attributi grafici.

#### D: Come posso salvare il documento PDF dopo aver disegnato le linee?

 A: Dopo aver aggiunto l'oggetto Grafico con gli oggetti Linea alla pagina, puoi salvare il documento PDF risultante utilizzando`pDoc.Save(dataDir + "DrawingLine_out.pdf");` riga nel codice sorgente fornito.

#### D: Posso disegnare linee con angoli e orientamenti diversi?

R: Sì, puoi disegnare linee con angoli e orientamenti diversi modificando le coordinate e le proprietà degli oggetti Linea nel Grafico.