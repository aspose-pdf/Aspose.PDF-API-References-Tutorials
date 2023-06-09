---
title: Casella di testo
linktitle: Casella di testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come creare un campo di testo in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 290
url: /it/net/programming-with-forms/text-box/
---

In questa guida spiegheremo passo dopo passo come utilizzare la libreria Aspose.PDF per .NET per creare un campo di testo in un documento PDF. Ti mostreremo come aprire il documento, creare il campo di testo, personalizzarne le proprietà e salvare il PDF modificato.

## Passaggio 1: configurazione della directory dei documenti

 Il primo passaggio consiste nel configurare la directory dei documenti in cui si trova il file PDF su cui si desidera lavorare. Puoi usare il`dataDir`variabile per specificare il percorso della directory.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 2: apertura del documento PDF

 In questo passaggio, apriremo il documento PDF utilizzando il file`Document`classe di Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Assicurarsi che il file PDF sia presente nella directory dei documenti specificata.

## Passaggio 3: creazione del campo di testo

 Creeremo un campo di testo utilizzando il`TextBoxField` classe. È possibile specificare le coordinate della posizione e le dimensioni del campo utilizzando il`Rectangle` classe.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Personalizza le coordinate, le dimensioni, il nome parziale e il valore del campo di testo secondo necessità.

## Passaggio 4: personalizzare le proprietà del campo di testo

In questo passaggio, personalizzeremo le proprietà del campo di testo come bordo, colore, ecc.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Personalizza le proprietà del campo di testo in base alle tue preferenze.

## Passaggio 5: aggiunta del campo al documento

Ora che abbiamo creato e configurato il campo di testo, possiamo aggiungerlo al documento PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Passaggio 6: salvare il PDF modificato

 Infine, possiamo salvare il PDF modificato utilizzando il file`Save` metodo del`Document` classe.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Assicurati di specificare il percorso completo e il nome del file per il PDF modificato.

### Esempio di codice sorgente per Casella di testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Crea un campo
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = nuovo bordo(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Aggiungi campo al documento
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Salva PDF modificato
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Conclusione

In questa guida, abbiamo imparato come utilizzare la libreria Aspose.PDF per .NET per creare un campo di testo in un documento PDF. Seguendo i passaggi descritti, è possibile personalizzare le proprietà del campo di testo e aggiungerlo al documento secondo necessità. Sentiti libero di esplorare ulteriormente le funzionalità di Aspose.PDF per .NET per espandere le possibilità di manipolazione dei file PDF.