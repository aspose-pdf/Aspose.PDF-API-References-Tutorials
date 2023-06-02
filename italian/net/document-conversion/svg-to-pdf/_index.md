---
title: SVG in PDF
linktitle: SVG in PDF
second_title: Aspose.PDF per riferimento API .NET
description: Facile e veloce conversione da SVG a PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 280
url: /it/net/document-conversion/svg-to-pdf/
---

Questo tutorial ti guiderà attraverso i passaggi per convertire un file SVG in un file PDF utilizzando Aspose.PDF per .NET. Aspose.PDF offre una soluzione semplice ed efficace per convertire i file SVG in PDF preservando la qualità e il layout dei contenuti. Seguire i passaggi seguenti per eseguire questa conversione.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: caricamento del file SVG
 Il primo passo è caricare il file SVG in un file`Document`oggetto utilizzando l'opzione di caricamento SVG (`SvgLoadOptions`). Usa il seguente codice:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea un'istanza dell'oggetto LoadOption utilizzando l'opzione di caricamento SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Crea oggetto documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file SVG.

## Passaggio 2: converti in PDF
 Il secondo passaggio consiste nel convertire il documento SVG in un documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Usa il seguente codice:

```csharp
// Salva il documento PDF risultante
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

Assicurati di specificare il percorso e il nome file desiderati per il file PDF risultante.

### Esempio di codice sorgente per SVG in PDF utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza dell'oggetto LoadOption utilizzando l'opzione di caricamento SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Crea oggetto documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// Salva il documento PDF risultante
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come convertire un file SVG in un file PDF utilizzando Aspose.PDF per .NET. Seguendo i passaggi sopra indicati, puoi eseguire facilmente questa conversione. Usa questo metodo per convertire i tuoi file SVG in PDF e goditi la flessibilità e la qualità di Aspose.PDF.