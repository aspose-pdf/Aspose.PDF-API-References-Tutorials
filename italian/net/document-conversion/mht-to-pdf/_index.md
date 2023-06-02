---
title: MHT in PDF
linktitle: MHT in PDF
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire MHT in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/document-conversion/mht-to-pdf/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file MHT in PDF utilizzando Aspose.PDF per .NET. MHT (MIME HTML) è un formato utilizzato per salvare una pagina Web completa, comprese le immagini e il contenuto associato. Seguendo i passaggi seguenti, sarai in grado di convertire i file MHT in formato PDF.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: caricamento del file MHT
In questo passaggio caricheremo il file MHT utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Carica il documento
Document document = new Document(dataDir + "test.mht", options);
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file MHT.

## Passaggio 2: conversione da MHT a PDF
Dopo aver caricato il file MHT, possiamo procedere con la conversione in PDF. Usa il seguente codice:

```csharp
// Salva l'output come documento PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Il codice sopra converte il file MHT in formato PDF e lo salva come nome file`"MHTToPDF_out.pdf"`.

### Esempio di codice sorgente per MHT in PDF utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Carica documento
Document document = new Document(dataDir  + "test.mht", options);
// Salva l'output come documento PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file MHT in PDF utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire i file MHT in formato PDF. Questa funzione può essere utile quando è necessario convertire intere pagine Web in documenti PDF.