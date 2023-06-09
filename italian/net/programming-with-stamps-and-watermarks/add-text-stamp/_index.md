---
title: Aggiungi timbro di testo
linktitle: Aggiungi timbro di testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere facilmente un timbro di testo ai tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere un timbro di testo a un documento PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per aggiungere un timbro di testo personalizzato a una pagina specifica del documento PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: caricamento del documento PDF

Il primo passaggio consiste nel caricare il documento PDF esistente nel progetto. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: creazione del buffer di testo

Ora che hai caricato il documento PDF, puoi creare il timbro di testo da aggiungere. Ecco come farlo:

```csharp
// Crea il buffer di testo
TextStamp textStamp = new TextStamp("Example Stamp");
```

Il codice precedente crea un nuovo buffer di testo contenente il testo specificato.

## Passaggio 4: configurazione delle proprietà del timbro di testo

Prima di aggiungere il timbro di testo al documento PDF, puoi configurare varie proprietà del timbro, come sfondo, posizione, rotazione, carattere, dimensione, ecc. Ecco come:

```csharp
// Configura le proprietà del buffer di testo
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

È possibile regolare queste proprietà in base alle proprie esigenze.

## Passaggio 5: aggiungi il timbro di testo al PDF

Ora che il timbro di testo è pronto, puoi aggiungerlo a una pagina specifica del documento PDF. Ecco come:

```csharp
// Aggiungi buffer di testo a una pagina specifica
pdfDocument.Pages[1].AddStamp(textStamp);
```

Il codice sopra aggiunge il timbro di testo alla prima pagina del documento PDF. È possibile specificare un'altra pagina, se necessario.

## Passaggio 6: salvare il documento di output

Una volta aggiunto il timbro di testo, è possibile salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento di output
pdfDocument.Save(dataDir);
```

Il codice sopra salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per Aggiungi timbro di testo utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Crea timbro di testo
TextStamp textStamp = new TextStamp("Sample Stamp");

// Imposta se il timbro è lo sfondo
textStamp.Background = true;

// Imposta origine
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Ruota timbro
textStamp.Rotate = Rotation.on90;

// Imposta le proprietà del testo
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Aggiungi timbro a una pagina particolare
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Salva documento di output
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere un timbro di testo utilizzando Aspose.PDF per .NET. Ora puoi applicare questa conoscenza ai tuoi progetti per aggiungere timbri di testo personalizzati ai documenti PDF.
