---
title: Da PDF a DOC
linktitle: Da PDF a DOC
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PDF in DOC utilizzando Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/document-conversion/pdf-to-doc/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file PDF in formato DOC utilizzando Aspose.PDF per .NET. I file PDF sono comunemente usati per visualizzare e condividere documenti universalmente, mentre il formato DOC è specifico di Microsoft Word. Seguendo i passaggi seguenti, sarai in grado di convertire i file PDF in formato DOC.

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
Document pdfDocument = new Document(dataDir + "PDFToDOC.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDF.

## Passo 2: Converti PDF in formato DOC
Dopo aver aperto il file PDF, possiamo procedere con la conversione in formato DOC. Usa il seguente codice:

```csharp
// Salva il file in formato documento MS
pdfDocument.Save(dataDir + "PDFToDOC_out.doc", SaveFormat.Doc);
```

 Il codice sopra converte il file PDF in formato DOC e lo salva come nome file`"PDFToDOC_out.doc"`.

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory desiderata in cui si desidera salvare il file DOC di output.

### Esempio di codice sorgente per PDF in DOC utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";          

// Apri il documento PDF di origine
Document pdfDocument = new Document(dataDir + "PDFToDOC.pdf");

//Salvare il file in formato documento MS
pdfDocument.Save(dataDir + "PDFToDOC_out.doc", SaveFormat.Doc);
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file PDF in formato DOC utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire i file PDF in formato DOC. Questa funzione può essere utile quando è necessario lavorare con file PDF in Microsoft Word o altre applicazioni che supportano il formato DOC.