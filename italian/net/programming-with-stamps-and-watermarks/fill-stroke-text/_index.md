---
title: Riempi il testo del tratto
linktitle: Riempi il testo del tratto
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come riempire e delineare facilmente il testo nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 90
url: /it/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
In questo tutorial, ti guideremo passo dopo passo su come riempire e delineare il testo in un documento PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per applicare i colori di riempimento e contorno al testo nel documento PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: creazione dell'oggetto TextState

Il primo passaggio consiste nel creare un oggetto TextState per passare le proprietà avanzate. Ecco come:

```csharp
// Crea un oggetto TextState per trasferire le proprietà avanzate
TextState ts = new TextState();

// Imposta il colore del contorno
ts.StrokingColor = Color.Gray;

// Definire la modalità di rendering del testo
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Il codice precedente crea un nuovo oggetto TextState e imposta il colore del contorno e la modalità di rendering del testo.

## Passaggio 3: caricamento del documento PDF

Ora che l'oggetto TextState è pronto, possiamo caricare il documento PDF in cui vogliamo applicare il riempimento e il contorno del testo. Ecco come:

```csharp
// Carica il documento PDF come input
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Il codice precedente carica il documento PDF esistente utilizzando la classe PdfFileStamp dalla libreria Aspose.PDF.Facades.

## Passaggio 4: aggiungi riempimento e tratto al testo

Ora che il documento PDF è caricato, possiamo aggiungere il riempimento e il contorno al testo. Ecco come:

```csharp
// Creare un timbro (Timbro) con il testo e le proprietà definiti
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Associa l'oggetto TextState
stamp.BindTextState(ts);

// Impostare l'origine X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Aggiungi il timbro al documento
fileStamp.AddStamp(stamp);
```

Il codice precedente crea un timbro con il testo specificato e le proprietà Fill e Stroke definite.

## Passaggio 5: salvare il documento di output

Una volta aggiunto il timbro di testo, possiamo salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento modificato
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Il codice precedente salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per Fill Stroke Text utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un oggetto TextState per trasferire le proprietà avanzate
TextState ts = new TextState();

// Imposta il colore per il tratto
ts.StrokingColor = Color.Gray;

// Imposta la modalità di rendering del testo
ts.RenderingMode = TextRenderingMode.StrokeText;

//Carica un documento PDF di input
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Associa TextState
stamp.BindTextState(ts);

// Imposta l'origine X,Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Aggiungi timbro
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Conclusione

Congratulazioni! Hai imparato a riempire e delineare il testo in un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi applicare questa conoscenza per personalizzare i colori di riempimento e contorno nei tuoi documenti PDF.
