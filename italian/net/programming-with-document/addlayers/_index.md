---
title: Aggiungi livelli
linktitle: Aggiungi livelli
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere livelli ai file PDF utilizzando Aspose.PDF per .NET. Guida dettagliata con esercitazioni sul codice per la creazione e il salvataggio di PDF a più livelli.
type: docs
weight: 20
url: /it/net/programming-with-document/addlayers/
---

Per aggiungere livelli a un file PDF, utilizzeremo Aspose.PDF per .NET. Questa libreria ci consente di lavorare efficacemente con i file PDF nelle applicazioni .NET. Segui le istruzioni dettagliate di seguito per aggiungere livelli utilizzando Aspose.PDF per .NET.

## Passaggio 1: crea un nuovo documento PDF

 Inizia creando una nuova istanza di`Document` classe fornita da Aspose.PDF per .NET. Questo servirà come documento PDF in cui aggiungeremo i livelli.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Passaggio 2: aggiungi una pagina al documento

Successivamente, aggiungi una pagina al documento utilizzando il file`Add` metodo del`Pages` raccolta nel`Document` classe.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 3: creare e aggiungere livelli alla pagina

 Crea istanze di`Layer` class per ogni livello che si desidera aggiungere al file PDF. Specificare un identificatore univoco e un nome per ogni livello.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

In questo tutorial, abbiamo aggiunto alla pagina tre livelli con colori e nomi diversi.

## Passaggio 4: salvare il file PDF

 Salvare il file PDF modificato utilizzando il file`Save` metodo del`Document` classe.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

Questo codice salverà il file PDF modificato nella directory specificata.

### Codice sorgente di esempio per l'aggiunta di livelli alle pagine PDF utilizzando Aspose.PDF per .NET

```csharp            
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Conclusione

In questo articolo, abbiamo fornito una guida passo passo per aggiungere livelli ai file PDF utilizzando Aspose.PDF per .NET. Seguendo le istruzioni e utilizzando i tutorial sul codice forniti, puoi incorporare facilmente i livelli nei tuoi documenti PDF. I livelli ti consentono di organizzare e controllare la visibilità dei contenuti, fornendo un'esperienza più interattiva e personalizzabile per i tuoi utenti.