---
title: Da PDF a SVG
linktitle: Da PDF a SVG
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PDF in SVG utilizzando Aspose.PDF per .NET.
type: docs
weight: 180
url: /it/net/document-conversion/pdf-to-svg/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un PDF in formato SVG utilizzando Aspose.PDF per .NET. SVG (Scalable Vector Graphics) è un formato di immagine vettoriale che aiuta a mantenere la qualità e il ridimensionamento della grafica. Seguendo i passaggi seguenti, sarai in grado di convertire un file PDF in formato SVG.

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
Document doc = new Document(dataDir + "input.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDF.

## Passaggio 2: creazione di un'istanza delle opzioni di salvataggio SVG
Dopo aver caricato il file PDF, creeremo un'istanza delle opzioni di salvataggio SVG. Usa il seguente codice:

```csharp
// Crea un'istanza di un oggetto SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Non comprimere l'immagine SVG in un archivio Zip
saveOptions.CompressOutputToZipArchive = false;
```

## Passaggio 3: salvataggio del file SVG risultante
Ora salveremo il file PDF convertito in formato SVG. Usa il seguente codice:

```csharp
// Salva l'output in file SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 Il codice sopra salva il PDF convertito in formato SVG con il nome del file`"PDFToSVG_out.svg"`.

### Esempio di codice sorgente per PDF in SVG utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica documento PDF
Document doc = new Document(dataDir + "input.pdf");
// Crea un'istanza di un oggetto di SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Non comprimere l'immagine SVG nell'archivio Zip
saveOptions.CompressOutputToZipArchive = false;
// Salva l'output in file SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file PDF in formato SVG utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire un file PDF in formato SVG. Questa funzione è utile quando si desidera mantenere la qualità grafica e il ridimensionamento durante la conversione in immagini vettoriali.