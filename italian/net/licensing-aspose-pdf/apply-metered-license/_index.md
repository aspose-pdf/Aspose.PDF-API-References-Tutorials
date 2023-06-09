---
title: Configura licenza a consumo
linktitle: Configura licenza a consumo
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata per impostare una licenza misurata con Aspose.PDF per .NET e beneficiare delle funzionalità avanzate.
type: docs
weight: 10
url: /it/net/licensing-aspose-pdf/configure-metered-license/
---

In questo tutorial, ti guideremo passo dopo passo su come impostare una licenza a consumo con Aspose.PDF per .NET. La licenza misurata consente di utilizzare le funzionalità avanzate di Aspose.PDF in base al consumo effettivo.

### Passaggio 1: configurazione delle chiavi di licenza

Nel codice sorgente fornito, è necessario specificare le chiavi pubbliche e private della licenza a consumo. Sostituisci il "*****" valori con le tue chiavi. Queste chiavi ti verranno fornite quando acquisti una licenza misurata da Aspose.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### Passaggio 2: caricamento del documento

 Carica il documento PDF dal disco utilizzando il file`Document`classe di Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### Passaggio 3: ottieni il conteggio delle pagine del documento

 Usa il`Count` proprietà del`Pages` collection per ottenere il numero totale di pagine nel documento.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### Esempio di codice sorgente per configurare la licenza a consumo utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// impostare chiavi pubbliche e private misurate
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
// Accedi alla proprietà setMeteredKey e passa chiavi pubbliche e private come parametri
metered.SetMeteredKey("*****", "*****");
// Carica il documento dal disco.
Document doc = new Document(dataDir + "input.pdf");
//Ottenere il conteggio delle pagine del documento
Console.WriteLine(doc.Pages.Count);

```

## Conclusione

In questo tutorial, abbiamo spiegato come impostare una licenza a consumo con Aspose.PDF per .NET. Utilizzando una licenza misurata, puoi beneficiare delle funzionalità avanzate di Aspose.PDF in base al tuo utilizzo effettivo. Assicurati di fornire chiavi di licenza valide per utilizzare Aspose.PDF con tutte le sue funzionalità.
