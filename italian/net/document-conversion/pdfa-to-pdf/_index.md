---
title: Da PDFA a PDF
linktitle: Da PDFA a PDF
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PDFA in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/document-conversion/pdfa-to-pdf/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file PDFA (PDF/A) in formato PDF standard utilizzando Aspose.PDF per .NET. Il formato PDFA è una versione specifica del formato PDF utilizzato per garantire l'archiviazione a lungo termine dei documenti. Seguendo i passaggi seguenti, sarai in grado di convertire un file PDFA in formato PDF.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: caricamento del documento PDFA
In questo passaggio, caricheremo il file PDFA di origine utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento PDFA
Document doc = new Document(dataDir + "PDFAToPDF.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDFA.

## Passaggio 2: rimozione delle informazioni sulla conformità PDF/A
Ora rimuoveremo le informazioni sulla conformità PDF/A dal documento. Usa il seguente codice:

```csharp
// Elimina le informazioni sulla conformità PDF/A
doc.RemovePdfaCompliance();
```

## Passaggio 3: salvare il file PDF risultante
Infine, salveremo il file PDFA convertito in formato PDF. Usa il seguente codice:

```csharp
// Salva il documento aggiornato in formato PDF
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

Il codice sopra salva il file PDFA convertito in formato PDF con il nome del file`"PDFAToPDF_out.pdf"`.

### Esempio di codice sorgente per PDFA in PDF utilizzando Aspose.Words per .NET


```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document doc = new Document(dataDir + "PDFAToPDF.pdf");

// Rimuovere le informazioni sulla conformità PDF/A
doc.RemovePdfaCompliance();
// Salva documento aggiornato
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file PDFA in formato PDF utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire un file PDFA nel formato PDF standard. Questa funzione è utile quando si desidera rimuovere le restrizioni di conformità PDF/A da un documento per un utilizzo più flessibile.