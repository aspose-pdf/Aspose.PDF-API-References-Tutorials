---
title: Da PDF a XLS
linktitle: Da PDF a XLS
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PDF in XLS utilizzando Aspose.PDF per .NET.
type: docs
weight: 200
url: /it/net/document-conversion/pdf-to-xls/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file PDF in formato XLS (Microsoft Excel) utilizzando Aspose.PDF per .NET. Seguendo i passaggi seguenti, sarai in grado di convertire un file PDF in formato XLS.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: caricamento del documento PDF
In questo passaggio caricheremo il file PDF di origine utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDF.

## Passaggio 2: crea un'istanza delle opzioni di backup di Excel
Dopo aver caricato il file PDF, creeremo un'istanza delle opzioni di salvataggio di Excel. Usa il seguente codice:

```csharp
// Creare un'istanza di un oggetto ExcelSaveOptions
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();
```

## Passaggio 3: salvataggio del file XLS risultante
Ora salveremo il file PDF convertito in formato XLS. Usa il seguente codice:

```csharp
// Salva l'output in formato XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

 Il codice sopra salva il file PDF convertito in formato XLS con il nome del file`"PDFToXLS_out.xls"`.

### Esempio di codice sorgente per PDF in XLS utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Crea un'istanza dell'oggetto opzione ExcelSave
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

// Salva l'output in formato XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file PDF in formato XLS utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire un file PDF in formato XLS. Questa funzione è utile quando si desidera estrarre dati tabulari da un file PDF e utilizzarli in Microsoft Excel.