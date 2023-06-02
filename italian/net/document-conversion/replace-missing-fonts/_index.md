---
title: Sostituisci i caratteri mancanti
linktitle: Sostituisci i caratteri mancanti
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata per sostituire i caratteri mancanti in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 260
url: /it/net/document-conversion/replace-missing-fonts/
---

In questo tutorial, ti guideremo attraverso il processo di sostituzione dei caratteri mancanti in un file PDF utilizzando Aspose.PDF per .NET. Quando si apre un file PDF su una macchina in cui manca un carattere specifico, potrebbero verificarsi problemi di visualizzazione del carattere. In tali casi è possibile sostituire il font mancante con un altro font disponibile sulla macchina. Seguendo i passaggi seguenti, sarai in grado di sostituire i caratteri mancanti in un file PDF.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: trovare il carattere mancante
Il primo passo è trovare il carattere mancante nel file PDF. Usa il seguente codice:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Trova il carattere originale
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // Il carattere non è presente sulla macchina di destinazione
     // Aggiungi una semplice sostituzione dei caratteri
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDF.

## Passaggio 2: sostituisci il carattere mancante
Successivamente, sostituiremo il font mancante con un altro font disponibile. Usa il seguente codice:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Converti il file PDF in formato PDF/A con la rimozione degli errori
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Salva il file PDF risultante
pdf.Save(fileNew.FullName);
```

 Assicurati di sostituire`"input.pdf"` con il percorso effettivo del file PDF originale e`"newfile_out.pdf"` con il nome desiderato per il file PDF risultante.

## Passaggio 3: salvare il file PDF risultante
Infine, salveremo il file PDF risultante con il carattere sostituito. Usa il seguente codice:

```csharp
// Salva il file PDF risultante
pdf.Save(fileNew.FullName);
```

Assicura di aver impostato il percorso di destinazione corretto per il file PDF risultante.

### Codice sorgente di esempio per sostituire i caratteri mancanti utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// Carattere mancante sul computer di destinazione
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di sostituzione dei caratteri mancanti in un file PDF utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, sarai in grado di sostituire con successo i font mancanti nel tuo file PDF.