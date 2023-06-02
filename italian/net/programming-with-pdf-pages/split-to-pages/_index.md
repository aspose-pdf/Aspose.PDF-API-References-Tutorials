---
title: Dividi in pagine
linktitle: Dividi in pagine
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET.
type: docs
weight: 140
url: /it/net/programming-with-pdf-pages/split-to-pages/
---
In questo tutorial, ti guideremo attraverso il processo passo-passo per dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come suddividere un documento PDF in più file PDF, ciascuno contenente una singola pagina.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza di base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Qui è dove si trova il documento PDF che vuoi dividere. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il documento PDF
 Quindi puoi aprire il documento PDF da dividere usando il file`Document` classe di Aspose.PDF. Assicurati di specificare il percorso del documento corretto.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## Passaggio 3: sfoglia le pagine e dividile
Ora puoi scorrere tutte le pagine del documento PDF usando un ciclo. Per ogni pagina, crea un nuovo documento e aggiungi quella pagina a questo nuovo documento. Quindi salvare il nuovo documento utilizzando un nome file univoco per ogni pagina.

```csharp
int pageCount = 1;
foreach(Page pdfPage in pdfDocument.Pages)
{
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
pageCount++;
}
```

### Esempio di codice sorgente per Split To Pages utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// Scorri tutte le pagine
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## Conclusione
In questo tutorial, abbiamo imparato come dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET. Seguendo questa guida passo-passo, puoi dividere facilmente un documento PDF in più file PDF, ciascuno contenente una singola pagina. Aspose.PDF offre un'API potente e flessibile per lavorare con i documenti PDF nei tuoi progetti. Ora puoi utilizzare questa funzione per eseguire operazioni di suddivisione di documenti PDF in base alle tue esigenze specifiche.
