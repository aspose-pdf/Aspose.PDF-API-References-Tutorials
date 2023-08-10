---
title: Riempi il testo del tratto nel file PDF
linktitle: Riempi il testo del tratto nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come riempire e delineare facilmente il testo nel file PDF con Aspose.PDF per .NET.
type: docs
weight: 90
url: /it/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
In questo tutorial, ti guideremo passo dopo passo su come riempire e delineare il testo nel file PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per applicare i colori di riempimento e contorno al testo nel file PDF.

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

Congratulazioni! Hai imparato a riempire e delineare il testo in un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi applicare questa conoscenza per personalizzare i colori di riempimento e contorno nei tuoi documenti PDF.

### Domande frequenti per il testo del tratto di riempimento nel file PDF

#### D: Cosa significa riempire e delineare il testo in un documento PDF e quando potrebbe essere necessario farlo?

R: Riempire e delineare il testo in un documento PDF comporta l'applicazione di colori all'interno dei caratteri del testo (riempimento) e ai bordi attorno al testo (contorno). Questo può essere utilizzato per migliorare l'aspetto visivo del testo, creare enfasi o evidenziare contenuti specifici all'interno del PDF.

#### D: In che modo il codice sorgente C# fornito esegue il riempimento e la struttura del testo in un file PDF?

 R: Il codice sorgente fornito mostra come creare un file`TextState` oggetto per definire le proprietà avanzate del testo, come il colore del contorno e la modalità di rendering. Utilizza quindi Aspose.PDF.Facades per caricare un documento PDF esistente, creare un timbro contenente il testo con le proprietà di riempimento e traccia specificate e aggiungere il timbro al documento.

####  D: Qual è lo scopo del`TextState` object in the code?

 R: Il`TextState`viene utilizzato per definire proprietà avanzate del testo, incluso il colore del contorno del testo (tratto) e la modalità di rendering. Ti consente di personalizzare l'aspetto del testo in termini di tratto e riempimento.

#### D: Posso applicare colori di riempimento e contorno diversi a parti diverse dello stesso testo?

 A: Sì, puoi modificare il codice per crearne uno diverso`TextState` oggetti con colori di riempimento e contorno distinti e applicarli a parti specifiche del testo utilizzando separato`Stamp` oggetti.

#### D: Posso applicare i colori di riempimento e contorno al testo già presente nel documento PDF?

 R: Sì, è possibile utilizzare principi simili per applicare i colori di riempimento e contorno al testo esistente nel documento PDF selezionando gli oggetti di testo appropriati e aggiungendoli come timbri con l'impostazione desiderata.`TextState` proprietà.

#### D: Come posso regolare l'opacità e la fusione del testo pieno e bordato?

 R: Il codice fornito consente di impostare le proprietà di opacità e sfumatura del timbro utilizzando il`Opacity` E`BlendingSpace`proprietà, rispettivamente. È possibile regolare questi valori per ottenere l'effetto visivo desiderato.

#### D: Come posso applicare diversi colori di riempimento e contorno a più timbri all'interno dello stesso documento PDF?

 R: Puoi crearne più di uno`TextState` oggetti con diversi colori di riempimento e contorno, quindi creare oggetti separati`Stamp` oggetti per ogni set di testo con colori distinti. Aggiungi questi timbri allo stesso documento PDF utilizzando il file`PdfFileStamp` classe.

#### D: Posso utilizzare caratteri diversi da Arial per il testo bordato e riempito?

 R: Sì, puoi cambiare il carattere modificando il parametro del nome del carattere nel file`FormattedText` costruttore durante la creazione del timbro. Puoi utilizzare qualsiasi tipo di carattere disponibile sul tuo sistema.

#### D: Come posso modificare l'angolo di rotazione del testo bordato e riempito?

 R: Il codice fornito consente di impostare l'angolo di rotazione del timbro utilizzando il`Rotation` proprietà. È possibile regolare questa proprietà per specificare l'angolo di rotazione desiderato per il testo.

#### D: Come posso controllare la posizione e le dimensioni del testo bordato e riempito sulla pagina?

R: Puoi usare il`SetOrigin` metodo del`Stamp` oggetto per impostare le coordinate X e Y della posizione del timbro sulla pagina. Inoltre, puoi regolare la dimensione del carattere nel file`FormattedText` costruttore per controllare la dimensione del testo.