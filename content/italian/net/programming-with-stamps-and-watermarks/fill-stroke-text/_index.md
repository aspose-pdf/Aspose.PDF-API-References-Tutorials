---
title: Riempi il testo del tratto nel file PDF
linktitle: Riempi il testo del tratto nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come riempire e delineare facilmente il testo in un file PDF con Aspose.PDF per .NET.
type: docs
weight: 90
url: /it/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
In questo tutorial, ti guideremo passo dopo passo su come riempire e delineare il testo in un file PDF usando Aspose.PDF per .NET. Ti mostreremo come usare il codice sorgente C# fornito per applicare colori di riempimento e contorno al testo nel file PDF.

## Fase 1: Impostazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET è stata scaricata e a cui si fa riferimento nel progetto.

## Passaggio 2: creazione dell'oggetto TextState

Il primo passo è creare un oggetto TextState per passare le proprietà avanzate. Ecco come:

```csharp
// Crea un oggetto TextState per trasferire proprietà avanzate
TextState ts = new TextState();

// Imposta il colore del contorno
ts.StrokingColor = Color.Gray;

// Definisci la modalità di rendering del testo
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Il codice soprastante crea un nuovo oggetto TextState e imposta il colore del contorno e il modo in cui viene visualizzato il testo.

## Passaggio 3: caricamento del documento PDF

Ora che l'oggetto TextState è pronto, possiamo caricare il documento PDF in cui vogliamo applicare il riempimento e il contorno del testo. Ecco come:

```csharp
// Carica il documento PDF come input
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Il codice sopra carica il documento PDF esistente utilizzando la classe PdfFileStamp della libreria Aspose.PDF.Facades.

## Passaggio 4: aggiungere riempimento e tratto al testo

Ora che il documento PDF è caricato, possiamo aggiungere il riempimento e il contorno al testo. Ecco come:

```csharp
// Crea un timbro (Timbro) con il testo e le proprietà definiti
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Associa l'oggetto TextState
stamp.BindTextState(ts);

// Imposta origine X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Aggiungere il timbro al documento
fileStamp.AddStamp(stamp);
```

Il codice soprastante crea un timbro con il testo specificato e le proprietà Riempimento e Tratto definite.

## Passaggio 5: Salvare il documento di output

Una volta aggiunto il timbro di testo, possiamo salvare il documento PDF modificato. Ecco come:

```csharp
// Salvare il documento modificato
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Il codice soprastante salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per il testo Fill Stroke utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un oggetto TextState per trasferire proprietà avanzate
TextState ts = new TextState();

// Imposta il colore per il tratto
ts.StrokingColor = Color.Gray;

// Imposta la modalità di rendering del testo
ts.RenderingMode = TextRenderingMode.StrokeText;

// Carica un documento PDF di input
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

Congratulazioni! Hai imparato come riempire e delineare il testo in un documento PDF usando Aspose.PDF per .NET. Ora puoi applicare questa conoscenza per personalizzare i colori di riempimento e di contorno nei tuoi documenti PDF.

### Domande frequenti sul testo del tratto di riempimento nel file PDF

#### D: Cosa significa riempire e delineare il testo in un documento PDF e quando potrebbe essere necessario farlo?

R: Riempire e delineare il testo in un documento PDF comporta l'applicazione di colori all'interno dei caratteri del testo (riempimento) e ai bordi attorno al testo (contorno). Questo può essere utilizzato per migliorare l'aspetto visivo del testo, creare enfasi o evidenziare contenuti specifici all'interno del PDF.

#### D: In che modo il codice sorgente C# fornito riesce a riempire e delineare il testo in un file PDF?

 A: Il codice sorgente fornito dimostra come creare un`TextState` oggetto per definire proprietà di testo avanzate, come colore del contorno e modalità di rendering. Quindi usa Aspose.PDF.Facades per caricare un documento PDF esistente, creare un timbro contenente il testo con proprietà di riempimento e tratto specificate e aggiungere il timbro al documento.

####  D: Qual è lo scopo del`TextState` object in the code?

 A: Il`TextState`object viene utilizzato per definire proprietà di testo avanzate, tra cui il colore del contorno del testo (tratto) e la modalità di rendering. Consente di personalizzare il modo in cui il testo appare in termini di tratto e riempimento.

#### D: Posso applicare colori di riempimento e contorno diversi a parti diverse dello stesso testo?

 A: Sì, puoi modificare il codice per creare diversi`TextState` oggetti con colori di riempimento e contorno distinti e applicarli a parti specifiche del testo utilizzando colori separati`Stamp` oggetti.

#### D: Posso applicare colori di riempimento e contorno al testo già presente nel documento PDF?

 R: Sì, puoi usare principi simili per applicare colori di riempimento e contorno al testo esistente nel documento PDF selezionando gli oggetti di testo appropriati e aggiungendoli come timbri con il colore desiderato.`TextState` proprietà.

#### D: Come posso regolare l'opacità e la sfumatura del testo riempito e contornato?

 A: Il codice fornito consente di impostare l'opacità e le proprietà di fusione del timbro utilizzando`Opacity` E`BlendingSpace`proprietà, rispettivamente. È possibile regolare questi valori per ottenere l'effetto visivo desiderato.

#### D: Come posso applicare colori di riempimento e contorno diversi a più timbri nello stesso documento PDF?

 A: Puoi crearne più di uno`TextState` oggetti con diversi colori di riempimento e contorno, quindi creare separati`Stamp` oggetti per ogni set di testo con colori distinti. Aggiungere questi timbri allo stesso documento PDF utilizzando il`PdfFileStamp` classe.

#### D: Posso usare font diversi da Arial per il testo delineato e riempito?

 A: Sì, puoi cambiare il font modificando il parametro del nome del font nel`FormattedText` costruttore quando si crea il timbro. Puoi usare qualsiasi font disponibile sul tuo sistema.

#### D: Come posso modificare l'angolo di rotazione del testo contornato e riempito?

 A: Il codice fornito consente di impostare l'angolo di rotazione del timbro utilizzando il`Rotation` proprietà. Puoi regolare questa proprietà per specificare l'angolo di rotazione desiderato per il testo.

#### D: Come posso controllare la posizione e la dimensione del testo delineato e riempito sulla pagina?

 A: Puoi usare il`SetOrigin` metodo del`Stamp` oggetto per impostare le coordinate X e Y della posizione del timbro sulla pagina. Inoltre, puoi regolare la dimensione del carattere nel`FormattedText` costruttore per controllare la dimensione del testo.