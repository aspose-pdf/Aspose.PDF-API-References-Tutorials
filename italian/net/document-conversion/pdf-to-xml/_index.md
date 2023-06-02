---
title: Da PDF a XML
linktitle: Da PDF a XML
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire PDF in XML utilizzando Aspose.PDF per .NET.
type: docs
weight: 210
url: /it/net/document-conversion/pdf-to-xml/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file PDF in formato XML utilizzando Aspose.PDF per .NET. XML (eXtensible Markup Language) è un formato di dati utilizzato per archiviare e scambiare informazioni strutturate. Seguendo i passaggi seguenti, sarai in grado di convertire un file PDF in formato XML.

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

## Passaggio 2: salvataggio del file XML risultante
Ora salveremo il file PDF convertito in formato XML. Usa il seguente codice:

```csharp
// Salva output come XML
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

 Il codice precedente salva il file PDF convertito in formato XML con il nome del file`"PDFToXML_out.xml"`.

### Esempio di codice sorgente per PDF in XML utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
// Carica il file PDF di origine
Document doc = new Document(dataDir + "input.pdf");
// Salva l'output in formato XML
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file PDF in XML utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire un file PDF in formato XML. Questa funzione è utile quando si desidera estrarre contenuto strutturato da un file PDF ed elaborarlo in un formato XML per un uso successivo.