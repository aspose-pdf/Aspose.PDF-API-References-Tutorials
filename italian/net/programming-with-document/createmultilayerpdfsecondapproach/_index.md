---
title: Crea PDF multistrato Secondo approccio
linktitle: Crea PDF multistrato Secondo approccio
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come creare un PDF multistrato utilizzando Aspose.PDF per .NET. Guida dettagliata con codice sorgente per la creazione di PDF dinamici con testo e immagini.
type: docs
weight: 80
url: /it/net/programming-with-document/createmultilayerpdfsecondapproach/
---

In questo tutorial, esploreremo come creare un PDF multistrato utilizzando il secondo approccio in Aspose.PDF per .NET. Forniremo una guida passo passo con spiegazioni dettagliate e includeremo il codice sorgente completo. Seguendo questo tutorial, sarai in grado di generare documenti PDF con più livelli utilizzando la libreria Aspose.PDF nelle tue applicazioni .NET.

Ora, iniziamo con la guida passo-passo.

## Passaggio 1: configurare l'ambiente

Per cominciare, apri Visual Studio e crea un nuovo progetto C#. Assicurati di aver fatto riferimento alla libreria Aspose.PDF nel tuo progetto. Dopo aver configurato l'ambiente, sei pronto per procedere con il passaggio successivo.

## Passaggio 2: inizializza le variabili

In questo passaggio, inizializzeremo le variabili necessarie. Dobbiamo impostare il percorso della directory del documento e definire le variabili di colore per i livelli PDF. Ecco lo snippet di codice:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## Passaggio 3: creare un documento PDF

Successivamente, creeremo una nuova istanza della classe Aspose.Pdf.Document, che rappresenta un documento PDF. Ecco lo snippet di codice:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Passaggio 4: aggiungi una pagina al documento

In questo passaggio, aggiungeremo una nuova pagina al documento PDF. Ecco lo snippet di codice:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Passaggio 5: aggiungi testo alla pagina

Ora aggiungeremo un frammento di testo alla pagina. Il testo verrà visualizzato come un segmento di paragrafo 3 con un colore rosso. Ecco lo snippet di codice:

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## Passaggio 6: aggiungi un'immagine alla pagina

In questo passaggio, aggiungeremo un'immagine alla pagina. L'immagine verrà posizionata come una casella mobile con una dimensione specifica. Ecco lo snippet di codice:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## Passaggio 7: salva il PDF

In questo passaggio, salveremo il PDF in un file.

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### Codice sorgente di esempio per la creazione di un secondo approccio PDF multistrato utilizzando Aspose.PDF per .NET.

```csharp   
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

## Conclusione

In questo articolo, abbiamo imparato come creare un PDF multistrato utilizzando il secondo approccio di Aspose.PDF per .NET. Ti abbiamo fornito istruzioni dettagliate e il codice sorgente completo necessario per creare un PDF multistrato.