---
title: Pagina Redigere
linktitle: Pagina Redigere
second_title: Aspose.PDF per riferimento API .NET
description: Questo articolo spiega come redigere una pagina PDF utilizzando Aspose.PDF per .NET, incluse istruzioni dettagliate e codice sorgente di esempio.
type: docs
weight: 120
url: /it/net/annotations/redactpage/
---
Se stai cercando di redigere informazioni sensibili da un documento PDF utilizzando Aspose.PDF per .NET, sei fortunato! Ecco una guida passo passo per iniziare:

## Nel codice, imposta il percorso della directory in cui si trova il tuo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Apri il documento PDF:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Crea un'istanza RedactionAnnotation per un'area di pagina specifica:

```csharp
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
```

## Impostare il colore di riempimento, il colore del bordo e il colore del testo dell'annotazione di redazione:

```csharp
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
```

## Impostare il testo da stampare sull'annotazione di redazione e il suo allineamento:

```csharp
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Ripeti il testo sovrapposto sopra l'annotazione di redazione:

```csharp
annot.Repeat = true;
```

## Aggiungi l'annotazione alla raccolta di annotazioni della prima pagina:

```csharp
doc.Pages[1].Annotations.Add(annot);
```

## Appiattire l'annotazione e redigere i contenuti della pagina, ovvero rimuovere testo e immagini sotto l'annotazione redatta:

```csharp
annot.Redact();
```

## Imposta il percorso e il nome del file PDF di output:

```csharp
dataDir = dataDir + "RedactPage_out.pdf";
```

## Salva il documento PDF con la pagina redatta:

```csharp
doc.Save(dataDir);
```

Questo è tutto! Hai redatto con successo una pagina del tuo documento PDF utilizzando Aspose.PDF per .NET.

### Esempio di codice sorgente per Redact Page utilizzando Aspose.PDF per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document doc = new Document(dataDir + "input.pdf");

// Crea un'istanza RedactionAnnotation per un'area di pagina specifica
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
// Testo da stampare su annotazione redatto
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
// Ripeti Sovrapponi il testo sull'annotazione redigi
annot.Repeat = true;
// Aggiungi annotazione alla raccolta di annotazioni della prima pagina
doc.Pages[1].Annotations.Add(annot);
// Appiattisce le annotazioni e oscura i contenuti della pagina (ovvero rimuove testo e immagine
// Sotto annotazione redatta)
annot.Redact();
dataDir = dataDir + "RedactPage_out.pdf";
doc.Save(dataDir);
```