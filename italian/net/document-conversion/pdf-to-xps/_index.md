---
title: Da PDF a XPS
linktitle: Da PDF a XPS
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PDF in XPS utilizzando Aspose.PDF per .NET.
type: docs
weight: 220
url: /it/net/document-conversion/pdf-to-xps/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file PDF in formato XPS (XML Paper Specification) utilizzando Aspose.PDF per .NET. Il formato XPS è un formato di file basato su XML utilizzato per rappresentare elettronicamente i documenti. Seguendo i passaggi seguenti, sarai in grado di convertire un file PDF in formato XPS.

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

## Passaggio 2: crea un'istanza delle opzioni di salvataggio XPS
Dopo aver caricato il file PDF, creeremo un'istanza delle opzioni di salvataggio XPS. Usa il seguente codice:

```csharp
// Istanzia opzioni di salvataggio XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Passaggio 3: salvataggio del file XPS risultante
Ora salveremo il file PDF convertito in formato XPS. Usa il seguente codice:

```csharp
// Salva il documento XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Il codice precedente salva il file PDF convertito in formato XPS con il nome del file`"PDFToXPS_out.xps"`.


### Esempio di codice sorgente per PDF in XPS utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Istanzia le opzioni di salvataggio XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Salva il documento XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file PDF in formato XPS utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire un file PDF in formato XPS. Questa funzione è utile quando si desidera visualizzare o stampare documenti PDF in formato XPS.