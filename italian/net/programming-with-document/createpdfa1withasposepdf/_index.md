---
title: Crea PDF A1 con Aspose Pdf
linktitle: Crea PDF A1 con Aspose Pdf
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come creare un documento PDF A1 utilizzando Aspose.PDF per .NET. Guida dettagliata con codice sorgente C#. Ottimizza in modo efficiente i PDF.
type: docs
weight: 90
url: /it/net/programming-with-document/createpdfa1withasposepdf/
---

In questa guida dettagliata, spiegheremo come utilizzare Aspose.PDF per .NET per creare un documento PDF A1. Ti forniremo il codice sorgente C# necessario e le istruzioni per eseguire questa operazione.

## Passaggio 1: definire le variabili e importare gli spazi dei nomi

 Innanzitutto, definisci la variabile`dataDir` per rappresentare la directory in cui sono archiviati i documenti. Verrà utilizzato per specificare il percorso del file di output.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Successivamente, crea una nuova istanza di`Document` classe da Aspose.PDF.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Passaggio 2: aggiungi contenuto al PDF

In questo passaggio, aggiungeremo una pagina al documento PDF e inseriremo un frammento di testo contenente il testo "Hello World!".

```csharp
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
```

## Passaggio 3: salva il PDF in un flusso di memoria

Per convertire il formato PDF in PDF/A1, dobbiamo salvarlo in un flusso di memoria.

```csharp
MemoryStream ms = new MemoryStream();
pdf1.Save(ms);
```

## Passo 4: Converti il PDF in formato PDF/A1

 Ora convertiremo il formato PDF in PDF/A1 utilizzando il file`Convert` metodo del`Document` classe. Passiamo un nuovo flusso di memoria come flusso di output e specifichiamo il file`PdfFormat.PDF_A_1A` formato.

```csharp
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
```

## Passaggio 5: salva il PDF convertito

Infine, salva il PDF convertito nella directory specificata.

```csharp
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

### Esempio di codice sorgente per Crea PDF A1 utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Aggiungi una pagina nel documento pdf
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
MemoryStream ms = new MemoryStream();
// Salva il documento
pdf1.Save(ms);
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

Seguendo questi passaggi e utilizzando il codice sorgente fornito, è possibile creare un documento PDF A1 utilizzando Aspose.PDF per .NET.

Ricordati di regolare la "CARTELLA DEL TUO DOCUMENTO" con il percorso della directory appropriato in cui desideri salvare il file di output.


