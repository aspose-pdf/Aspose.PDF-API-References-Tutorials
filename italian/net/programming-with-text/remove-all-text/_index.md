---
title: Rimuovi tutto il testo
linktitle: Rimuovi tutto il testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come rimuovere tutto il testo da un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 280
url: /it/net/programming-with-text/remove-all-text/
---

In questo tutorial, spiegheremo come rimuovere tutto il testo da un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguiremo il processo passo-passo di apertura di un PDF, selezione ed eliminazione del testo da ogni pagina e salvataggio del PDF modificato utilizzando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di disporre di quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, devi impostare il percorso della directory in cui si trovano i tuoi file PDF. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso dei file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento PDF

 Successivamente, apriamo il documento PDF utilizzando il file`Document` class dalla libreria Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Passaggio 3: rimuovi il testo da ogni pagina

 Passiamo in rassegna tutte le pagine del documento PDF e utilizziamo un file`OperatorSelector` per selezionare tutto il testo su ciascuna pagina. Quindi, eliminiamo il testo selezionato.

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## Passaggio 4: salvare il PDF modificato

Infine, salviamo il documento PDF modificato nel file di output specificato.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Esempio di codice sorgente per Rimuovi tutto il testo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Passa attraverso tutte le pagine del documento PDF
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	// Seleziona tutto il testo della pagina
	page.Contents.Accept(operatorSelector);
	// Elimina tutto il testo
	page.Contents.Delete(operatorSelector.Selected);
}
// Salva il documento
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusione

In questo tutorial, hai imparato come rimuovere tutto il testo da un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida dettagliata ed eseguendo il codice C# fornito, puoi aprire un PDF, selezionare ed eliminare il testo da ogni pagina e salvare il PDF modificato.