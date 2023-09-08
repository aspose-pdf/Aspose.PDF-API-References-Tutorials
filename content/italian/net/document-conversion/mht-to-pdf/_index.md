---
title: MHT in PDF
linktitle: MHT in PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per convertire MHT in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/document-conversion/mht-to-pdf/
---
In questo tutorial, ti guideremo attraverso il processo di conversione di un file MHT in PDF utilizzando Aspose.PDF per .NET. MHT (MIME HTML) è un formato utilizzato per salvare una pagina Web completa, incluse immagini e contenuti associati. Seguendo i passaggi seguenti, sarai in grado di convertire i file MHT in formato PDF.

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

// Caricare il documento
Document document = new Document(dataDir + "test.mht", options);
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file MHT.

## Passaggio 2: conversione da MHT a PDF
Dopo aver caricato il file MHT, possiamo procedere con la conversione in PDF. Utilizza il seguente codice:

```csharp
// Salvare l'output come documento PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Il codice sopra converte il file MHT in formato PDF e lo salva come nome file`"MHTToPDF_out.pdf"`.

### Codice sorgente di esempio per MHT in PDF utilizzando Aspose.PDF per .NET

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
In questo tutorial, abbiamo trattato il processo passo passo di conversione di un file MHT in PDF utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire i file MHT in formato PDF. Questa funzionalità può essere utile quando è necessario convertire intere pagine Web in documenti PDF.

### Domande frequenti

#### D: Aspose.PDF per .NET supporta la conversione di file MHT con immagini incorporate in PDF?

R: Sì, Aspose.PDF per .NET supporta la conversione di file MHT con immagini incorporate in PDF. La libreria può gestire il contenuto completo della pagina Web, comprese le immagini e le risorse associate, e convertirlo in un documento PDF.

#### D: Posso personalizzare l'output PDF durante il processo di conversione da MHT a PDF?

R: Sì, Aspose.PDF per .NET fornisce varie opzioni per personalizzare l'output PDF durante il processo di conversione da MHT a PDF. Puoi impostare proprietà come dimensioni della pagina, orientamento, margini e altro per controllare l'aspetto del documento PDF risultante.

#### D: Aspose.PDF per .NET conserva i collegamenti ipertestuali e la formattazione del file MHT originale nell'output PDF?

R: Sì, Aspose.PDF per .NET conserva i collegamenti ipertestuali e la formattazione del file MHT originale nell'output PDF. La libreria garantisce che il PDF convertito mantenga lo stesso layout e contenuto del file MHT di origine.

#### D: Posso convertire più file MHT in documenti PDF separati utilizzando Aspose.PDF per .NET?

R: Sì, puoi convertire più file MHT in documenti PDF separati utilizzando Aspose.PDF per .NET. Carica semplicemente ciascun file MHT e salvalo come documento PDF separato con un nome file univoco.