---
title: Da PDF a XLS
linktitle: Da PDF a XLS
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per convertire PDF in XLS utilizzando Aspose.PDF per .NET.
type: docs
weight: 200
url: /it/net/document-conversion/pdf-to-xls/
---
In questo tutorial ti guideremo attraverso il processo di conversione di un file PDF in formato XLS (Microsoft Excel) utilizzando Aspose.PDF per .NET. Seguendo i passaggi seguenti, sarai in grado di convertire un file PDF in formato XLS.

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

## Passaggio 2: creare un'istanza delle opzioni di backup di Excel
Dopo aver caricato il file PDF, creeremo un'istanza delle opzioni di salvataggio di Excel. Utilizza il seguente codice:

```csharp
// Creare un'istanza di un oggetto ExcelSaveOptions
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();
```

## Passaggio 3: salvataggio del file XLS risultante
Ora salveremo il file PDF convertito in formato XLS. Utilizza il seguente codice:

```csharp
// Salva l'output in formato XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

 Il codice sopra salva il file PDF convertito in formato XLS con il nome file`"PDFToXLS_out.xls"`.

### Codice sorgente di esempio per PDF in XLS utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica il documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Crea un'istanza dell'oggetto Opzione ExcelSave
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

// Salva l'output in formato XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

## Conclusione
In questo tutorial, abbiamo trattato il processo passo passo di conversione di un file PDF in formato XLS utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire un file PDF in formato XLS. Questa funzionalità è utile quando si desidera estrarre dati tabulari da un file PDF e utilizzarli in Microsoft Excel.

### Domande frequenti

#### D: Aspose.PDF per .NET può convertire PDF con tabelle complesse e formattazione in formato XLS?

R: Sì, Aspose.PDF per .NET è progettato per gestire PDF con tabelle e formattazioni complesse. Durante il processo di conversione in formato XLS, Aspose.PDF per .NET cerca di preservare il layout e la struttura delle tabelle nel modo più accurato possibile, garantendo che i dati tabulari vengano estratti in modo efficace.

#### D: Cosa succede se il PDF contiene immagini o contenuto non tabellare?

A: Quando si converte un PDF in formato XLS, Aspose.PDF per .NET si concentra principalmente sull'estrazione dei dati tabulari. Il contenuto non tabellare, ad esempio immagini, annotazioni o testo in formato libero, potrebbe non essere conservato nel file XLS. Il file XLS risultante conterrà principalmente dati tabulari estratti dal PDF.

#### D: È possibile personalizzare l'aspetto e il layout del file XLS durante la conversione?

 R: Aspose.PDF per .NET fornisce opzioni per personalizzare l'aspetto e il layout del file XLS risultante. È possibile regolare varie impostazioni utilizzando le proprietà di`ExcelSaveOptions` classe, come specificare la cella iniziale per la tabella, impostare la codifica del testo e controllare altre opzioni relative all'output.

#### D: Posso convertire PDF protetti da password in formato XLS utilizzando Aspose.PDF per .NET?

 R: Sì, Aspose.PDF per .NET supporta la conversione di PDF protetti da password in formato XLS. Quando si carica un PDF protetto da password, è possibile fornire la password utilizzando il file`Document` costruttore della classe o impostando il file`Password` proprietà prima di caricare il PDF.