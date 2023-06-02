---
title: Crea PDF multistrato Primo approccio
linktitle: Crea PDF multistrato Primo approccio
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come creare documenti PDF multistrato utilizzando il primo approccio con Aspose.PDF per .NET. Aggiungi testo, immagini e altro per migliorare i tuoi PDF.
type: docs
weight: 70
url: /it/net/programming-with-document/createmultilayerpdffirstapproach/
---

In questo tutorial, ti guideremo attraverso il processo di creazione di un PDF multistrato utilizzando il primo approccio con Aspose.PDF per .NET. Questo approccio ti consente di aggiungere più livelli al tuo documento PDF. Segui la guida dettagliata di seguito:

## Passaggio 1: inizializza il documento PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## Passaggio 2: aggiungi una nuova pagina al documento

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## Passaggio 3: aggiungi un frammento di testo alla pagina

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## Passaggio 4: personalizzare il frammento di testo

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## Passaggio 5: aggiungi un'immagine alla pagina

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## Passaggio 6: aggiungi una casella mobile alla pagina

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## Passaggio 7: salvare il documento PDF risultante

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Congratulazioni! Hai creato con successo un documento PDF multistrato utilizzando il primo approccio con Aspose.PDF per .NET.

### Codice sorgente di esempio per Crea PDF multistrato Primo approccio utilizzando Aspose.PDF per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);

t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;

Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);

pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Ora puoi creare documenti PDF multistrato utilizzando il primo approccio con Aspose.PDF per .NET.
