---
title: Linea di disegno
linktitle: Linea di disegno
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come tracciare una linea su una pagina utilizzando Aspose.PDF per .NET. Guida passo passo alla creazione di linee personalizzate.
type: docs
weight: 80
url: /it/net/programming-with-graphs/drawing-line/
---
In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per tracciare una linea usando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di configurare il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

## Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, è necessario specificare la directory in cui si desidera salvare il file PDF risultante. Modificare la variabile "dataDir" nella directory desiderata.

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

Impostiamo i margini della pagina su 0 su tutti i lati.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Passaggio 4: creazione di un oggetto grafico e della prima riga

Creiamo un oggetto Graph con dimensioni uguali a quelle della pagina e disegniamo la prima linea che va dall'angolo in basso a sinistra all'angolo in alto a destra della pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Passaggio 5: tracciare la seconda linea

Disegniamo la seconda linea che va dall'angolo in alto a sinistra all'angolo in basso a destra della pagina.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Passaggio 6: aggiunta dell'oggetto grafico alla pagina

Aggiungiamo l'oggetto Graph alla collezione di paragrafi della pagina.

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

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza di documento
Document pDoc = new Document();
// Aggiungi pagine alla raccolta di pagine di documenti PDF
Page pg = pDoc.Pages.Add();
// Imposta il margine della pagina su tutti i lati come 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Crea un oggetto grafico con larghezza e altezza uguali alle dimensioni della pagina
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Crea l'oggetto della prima riga partendo dall'angolo in basso a sinistra fino all'angolo in alto a destra della pagina
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Aggiungi una linea alla raccolta di forme dell'oggetto grafico
graph.Shapes.Add(line);
// Disegna una linea dall'angolo superiore sinistro della pagina all'angolo inferiore destro della pagina
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Aggiungi una linea alla raccolta di forme dell'oggetto grafico
graph.Shapes.Add(line2);
// Aggiungi oggetto grafico alla raccolta di paragrafi della pagina
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Salva file PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Conclusione

In questo tutorial, abbiamo spiegato come disegnare una linea usando Aspose.PDF per .NET. Ora puoi usare questa conoscenza per creare forme geometriche con linee personalizzate nei tuoi file PDF.

### FAQ

#### D: Qual è lo scopo di questo tutorial?

A: Lo scopo di questo tutorial è di guidarti attraverso il processo di disegno delle linee usando Aspose.PDF per .NET. Imparerai come creare linee su una pagina PDF e personalizzarne l'aspetto.

#### D: Quali prerequisiti sono richiesti prima di iniziare?

A: Prima di iniziare, assicurati di aver installato la libreria Aspose.PDF e di aver impostato il tuo ambiente di sviluppo. Si consiglia inoltre una conoscenza di base della programmazione C#.

#### D: Come faccio a specificare la directory per salvare il file PDF?

R: Modifica la variabile "dataDir" nel codice sorgente fornito per indicare la directory in cui desideri salvare il file PDF risultante.

#### D: Come posso creare linee su una pagina PDF?

R: Il tutorial dimostra la creazione di un oggetto Graph con le dimensioni della pagina e quindi l'aggiunta di oggetti Line. Modificare le coordinate e le proprietà degli oggetti Linea per creare le linee desiderate.

#### D: Posso personalizzare l'aspetto delle linee?

R: Sì, puoi personalizzare l'aspetto delle linee modificando le proprietà degli oggetti Linea. Ciò include la modifica delle coordinate, del colore, dello spessore e di altri attributi grafici.

#### D: Come posso salvare il documento PDF dopo aver tracciato le linee?

R: Dopo aver aggiunto alla pagina l'oggetto Grafico con gli oggetti Linea, è possibile salvare il documento PDF risultante utilizzando il file`pDoc.Save(dataDir + "DrawingLine_out.pdf");` riga nel codice sorgente fornito.

#### D: Posso disegnare linee con angoli e orientamenti diversi?

R: Sì, puoi disegnare linee con angoli e orientamenti diversi regolando le coordinate e le proprietà degli oggetti Linea all'interno del grafico.