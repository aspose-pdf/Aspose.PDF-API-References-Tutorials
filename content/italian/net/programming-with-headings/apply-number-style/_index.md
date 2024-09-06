---
title: Applica stile numero nel file PDF
linktitle: Applica stile numero nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come applicare uno stile di numerazione alle intestazioni nei file PDF utilizzando Aspose.PDF per .NET. Guida passo passo.
type: docs
weight: 10
url: /it/net/programming-with-headings/apply-number-style/
---
In questo tutorial ti guideremo passo dopo passo attraverso il seguente codice sorgente C# per applicare lo stile di numerazione al file PDF utilizzando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di aver impostato il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

### Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, devi specificare la directory in cui vuoi salvare il file PDF generato. Cambia la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Fase 2: Creazione del documento PDF

Creiamo un nuovo documento PDF con dimensioni e margini specificati.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### Passaggio 3: creazione di una pagina e di un contenitore mobile

Aggiungiamo una pagina al documento e creiamo un contenitore mobile per organizzare il contenuto.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### Passaggio 4: aggiungere titoli con numerazione

Creiamo intestazioni con numerazioni specifiche e le aggiungiamo al contenitore mobile.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### Passaggio 5: salvataggio del documento PDF

Salviamo il documento PDF generato nella directory specificata.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Esempio di codice sorgente per applicare lo stile numerico utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Conclusione

In questo tutorial, abbiamo spiegato come applicare uno stile di numerazione alle intestazioni in un documento PDF usando Aspose.PDF per .NET. Ora puoi usare questa conoscenza per creare documenti PDF con numerazioni personalizzate per le intestazioni.

### Domande frequenti per applicare lo stile numerico nel file PDF

#### D: Cos'è lo stile di numerazione in un documento PDF?

A: Lo stile di numerazione si riferisce al formato in cui le intestazioni o le sezioni sono numerate in un documento PDF. Può includere numeri, lettere o altri caratteri per fornire una struttura gerarchica.

#### D: Perché dovrei applicare uno stile di numerazione alle intestazioni di un documento PDF?

A: Applicare lo stile di numerazione alle intestazioni migliora la leggibilità e l'organizzazione del documento PDF. Aiuta i lettori a navigare facilmente e a comprendere la struttura gerarchica del contenuto.

#### D: Che cos'è Aspose.PDF per .NET?

R: Aspose.PDF per .NET è una libreria che consente agli sviluppatori di lavorare con file PDF a livello di programmazione in applicazioni .NET. Fornisce un'ampia gamma di funzionalità per creare, modificare, convertire e manipolare documenti PDF.

#### D: Come posso importare le librerie necessarie per il mio progetto C#?

A: Per importare le librerie necessarie per il tuo progetto C#, includi le seguenti direttive di importazione:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Queste direttive consentono di accedere alle classi e ai metodi necessari per lavorare con i documenti PDF e applicare stili di numerazione.

#### D: Come faccio a specificare la directory in cui salvare il file PDF generato?

A: Nel codice sorgente fornito, modificare la variabile "dataDir" per specificare la directory in cui si desidera salvare il file PDF generato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory.

#### D: Come posso creare un documento PDF con dimensioni e margini specifici?

A: Per creare un documento PDF con dimensioni e margini specificati, utilizzare il seguente codice:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### D: Come posso aggiungere intestazioni con stile numerato al documento PDF?

A: Per aggiungere titoli con stile di numerazione al documento PDF, usa gli esempi di codice forniti per creare titoli e personalizzare i loro stili di numerazione. Regola proprietà come testo, stile di numerazione, numero di inizio e sequenza automatica come necessario.

#### D: Come posso salvare il documento PDF generato?

 A: Per salvare il documento PDF generato, utilizzare`Save` metodo del`pdfDoc` oggetto:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### D: Come posso confermare che lo stile di numerazione è stato applicato?

A: Aprire il file PDF generato per verificare che lo stile di numerazione specificato sia stato applicato alle intestazioni.

#### D: Posso personalizzare ulteriormente lo stile della numerazione?

 A: Sì, puoi personalizzare ulteriormente lo stile di numerazione modificando le proprietà del`Heading` oggetti, come il tipo di stile di numerazione, il numero di inizio e la sequenza automatica.

#### D: Posso applicare stili di numerazione diversi a sezioni diverse del documento?

 A: Sì, puoi applicare stili di numerazione diversi a sezioni diverse del documento creando più`Heading` oggetti con stili e sequenze diversi.