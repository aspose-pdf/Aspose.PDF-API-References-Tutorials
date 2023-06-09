---
title: Aggiungi timbro immagine
linktitle: Aggiungi timbro immagine
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere facilmente un timbro immagine ai tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 20
url: /it/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere un buffer di immagine a un documento PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per aggiungere un buffer immagine personalizzato a una pagina specifica nel documento PDF.

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
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: creazione del framebuffer

Ora che hai caricato il documento PDF, puoi creare il timbro dell'immagine da aggiungere. Ecco come farlo:

```csharp
// Crea il frame buffer
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

Il codice precedente crea un nuovo buffer immagine utilizzando il file "aspose-logo.jpg". Assicurati che il percorso del file immagine sia corretto.

## Passaggio 4: configurazione delle proprietà del buffer immagine

Prima di aggiungere il timbro immagine al documento PDF, è possibile configurare varie proprietà del timbro, come opacità, dimensione, posizione, ecc. Ecco come:

```csharp
// Configura le proprietà del buffer dell'immagine
imageStamp. Background = true;
imageStamp. XIndent = 100;
imageStamp. YIndent = 100;
imageStamp. Height = 300;
imageStamp. Width = 300;
imageStamp.Rotate = Rotate.on270;
imageStamp. Opacity = 0.5;
```

È possibile regolare queste proprietà in base alle proprie esigenze.

## Passaggio 5: aggiunta del timbro dell'immagine al PDF

Ora che il timbro dell'immagine è pronto, puoi aggiungerlo a una pagina specifica del documento PDF. Ecco come:

```csharp
// Aggiungi il frame buffer alla pagina specifica
pdfDocument.Pages[1].AddStamp(imageStamp);
```

Il codice sopra aggiunge il buffer dell'immagine alla prima pagina del documento PDF. È possibile specificare un'altra pagina, se necessario.

## Passaggio 6: salvare il documento di output

Dopo aver aggiunto il buffer dell'immagine, puoi salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento di output
pdfDocument.Save(dataDir);
```

Il codice precedente salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per Aggiungi timbro immagine utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "AddImageStamp.pdf");

// Crea timbro immagine
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
imageStamp.Background = true;
imageStamp.XIndent = 100;
imageStamp.YIndent = 100;
imageStamp.Height = 300;
imageStamp.Width = 300;
imageStamp.Rotate = Rotation.on270;
imageStamp.Opacity = 0.5;

// Aggiungi timbro a una pagina particolare
pdfDocument.Pages[1].AddStamp(imageStamp);
dataDir = dataDir + "AddImageStamp_out.pdf";

// Salva documento di output
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Hai imparato come aggiungere un buffer di immagine utilizzando Aspose.PDF per .NET. Ora puoi applicare questa conoscenza ai tuoi progetti per aggiungere timbri immagine personalizzati ai documenti PDF.
