---
title: Riempimento del testo arabo
linktitle: Riempimento del testo arabo
second_title: Aspose.PDF per riferimento API .NET
description: Compila facilmente i campi del modulo PDF con testo arabo utilizzando Aspose.PDF per .NET.
type: docs
weight: 20
url: /it/net/programming-with-forms/arabic-text-filling/
---

In questo tutorial, impareremo come popolare un campo modulo PDF con testo arabo utilizzando Aspose.PDF per .NET. Aspose.PDF è una potente libreria che consente agli sviluppatori di manipolare a livello di codice i documenti PDF. Ti guideremo attraverso il processo passo dopo passo, spiegando il codice sorgente C# necessario per eseguire questa operazione.

## Passaggio 1: caricare il contenuto del modulo PDF

Per prima cosa, dobbiamo caricare il modulo PDF che contiene il campo che vogliamo compilare. Iniziamo definendo il percorso della directory in cui si trova il modulo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Successivamente, creiamo un file`FileStream` oggetto per leggere e scrivere il file del modulo:

```csharp
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
```

 Successivamente, istanziamo a`Document` oggetto utilizzando il flusso che contiene il file del modulo:

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Passaggio 2: accedi al campo TextBoxField

 Per riempire il campo del modulo con testo arabo, dobbiamo accedere allo specifico`TextBoxField` campo che vogliamo riempire. In questo esempio, assumiamo che il nome del campo sia "textbox1". Possiamo recuperare il riferimento al campo utilizzando il file`Form` proprietà del`pdfDocument` oggetto:

```csharp
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Passo 3: Compila il campo del modulo con testo in arabo

 Ora che abbiamo il`TextBoxField` riferimento, possiamo assegnare il testo arabo al suo`Value` proprietà:

```csharp
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
```

## Passaggio 4: salvare il documento aggiornato

Infine, salviamo il documento aggiornato in un nuovo file:

```csharp
dataDir = dataDir + "ArabicTextFilling_out.pdf";
pdfDocument.Save(dataDir);
```

Visualizziamo anche un messaggio per indicare il successo della compilazione del testo arabo:

```csharp
Console.WriteLine("\nArabic text successfully filled in the form field.\nFile saved in the following location: " + dataDir);
```

### Codice sorgente di esempio per il riempimento del testo arabo utilizzando Aspose.Words per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il contenuto del modulo PDF
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
//Istanzia l'istanza del documento con il file del modulo contenente il flusso
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Ottieni il riferimento del particolare TextBoxField
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
// Compila il campo del modulo con testo arabo
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
dataDir = dataDir + "ArabicTextFilling_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, abbiamo esplorato come popolare un campo modulo PDF con testo arabo utilizzando Aspose.PDF per .NET. Abbiamo seguito il processo passo dopo passo e spiegato il codice sorgente C# pertinente. Seguendo queste istruzioni, puoi facilmente integrare la funzionalità di riempimento del testo in arabo nelle tue applicazioni .NET. Se hai ulteriori domande o hai bisogno di maggiori informazioni, non esitare a contattare il team di supporto di Aspose.PDF o controlla le risorse aggiuntive di seguito.