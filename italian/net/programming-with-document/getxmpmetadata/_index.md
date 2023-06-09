---
title: Ottieni metadati XMP
linktitle: Ottieni metadati XMP
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare la funzione GetXmpMetadata di Aspose.PDF per .NET per estrarre i metadati XMP da un documento PDF utilizzando il codice sorgente C#.
type: docs
weight: 200
url: /it/net/programming-with-document/getxmpmetadata/
---

 Aspose.PDF per .NET è una popolare libreria di manipolazione PDF che consente agli sviluppatori di creare, modificare e convertire file PDF nelle loro applicazioni .NET. Una delle funzionalità offerte da questa libreria è la possibilità di estrarre i metadati XMP da un documento PDF. Questo tutorial ti guiderà attraverso le fasi di utilizzo del`GetXmpMetadata` caratteristica di Aspose.PDF per .NET per estrarre i metadati XMP da un documento PDF.

## Passo 1: Installa Aspose.PDF per .NET

 Per utilizzare Aspose.PDF per .NET nelle tue applicazioni .NET, devi prima installare la libreria. È possibile scaricare l'ultima versione della libreria dal file[Pagina di download di Aspose.PDF per .NET](https://releases.aspose.com/pdf/net).

Una volta scaricata la libreria, estrai il contenuto del file ZIP in una cartella del tuo computer. Sarà quindi necessario aggiungere un riferimento alla DLL Aspose.PDF per .NET nel progetto .NET.

## Passaggio 2: caricare il documento PDF

 Dopo aver installato Aspose.PDF per .NET e aggiunto un riferimento alla DLL nel tuo progetto .NET, puoi iniziare a utilizzare il`GetXmpMetadata` funzione per estrarre i metadati XMP da un documento PDF.

Il primo passaggio per utilizzare questa funzione è caricare il documento PDF da cui si desidera estrarre i metadati XMP. Per fare ciò, puoi utilizzare il seguente codice:

```csharp
// Il percorso del documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri il documento PDF
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

 Nel codice sopra, sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui si trova il documento PDF. Questo codice caricherà il documento PDF in un file`Document` oggetto, che puoi quindi utilizzare per estrarre i metadati XMP.

## Passaggio 3: estrarre i metadati XMP

Per estrarre i metadati XMP da un documento PDF, puoi utilizzare il seguente codice:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Nel codice sopra,`xmp:CreateDate`, `xmp:Nickname` , E`xmp:CustomProperty`sono esempi di proprietà dei metadati XMP che è possibile estrarre da un documento PDF. Puoi sostituire questi nomi di proprietà con i nomi di qualsiasi altra proprietà di metadati XMP che desideri estrarre.

### Codice sorgente di esempio per ottenere metadati XMP utilizzando Aspose.PDF per .NET

 Ecco il codice sorgente completo per estrarre i metadati XMP da un documento PDF utilizzando il formato`GetXmpMetadata` caratteristica di Aspose.PDF per .NET:

```csharp
// Il percorso del documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri il documento PDF
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// Estrai i metadati XMP
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Nel codice sopra, sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui si trova il documento PDF. Questo codice estrarrà i metadati XMP dal documento PDF e li invierà alla console.