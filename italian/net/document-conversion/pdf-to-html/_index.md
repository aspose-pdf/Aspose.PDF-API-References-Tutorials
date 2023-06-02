---
title: PDF in HTML
linktitle: PDF in HTML
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PDF in HTML utilizzando Aspose.PDF per .NET.
type: docs
weight: 130
url: /it/net/document-conversion/pdf-to-html/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file PDF in formato HTML utilizzando Aspose.PDF per .NET. Il formato PDF è comunemente usato per visualizzare e condividere documenti, mentre il formato HTML è usato per creare pagine web. Seguendo i passaggi seguenti, sarai in grado di convertire i file PDF in formato HTML.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: apertura del documento PDF di origine
In questo passaggio, apriremo il file PDF di origine utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento PDF di origine
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDF.

## Passaggio 2: conversione da PDF a HTML
Dopo aver aperto il file PDF, possiamo procedere con la conversione in formato HTML. Usa il seguente codice:

```csharp
// Salva il file in formato HTML
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

 Il codice sopra converte il file PDF in formato HTML e lo salva come`"output_out.html"` file.

 Sostituire`"YOUR DOCUMENTS DIRECTORY"`con la directory desiderata in cui si desidera salvare il file HTML di output.

### Esempio di codice sorgente per PDF in HTML utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri il documento PDF di origine
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");

//Salvare il file in formato documento MS
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file PDF in formato HTML utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire i file PDF in formato HTML. Questa funzione è utile quando si desidera incorporare contenuto PDF in pagine Web o altre applicazioni che supportano il formato HTML.

