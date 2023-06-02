---
title: Adatta al contenuto della pagina
linktitle: Adatta al contenuto della pagina
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata dettagliata per la regolazione del contenuto della pagina PDF utilizzando Aspose.PDF per .NET. Facile implementazione e conclusione gratificante.
type: docs
weight: 50
url: /it/net/programming-with-pdf-pages/fit-page-contents/
---
In questo tutorial, ti guideremo attraverso il processo passo-passo per regolare il contenuto della pagina PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come regolare il contenuto delle pagine PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza di base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui si trova il file PDF di input. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento PDF
 Quindi puoi caricare il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto del file PDF di input.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 3: modifica il contenuto della pagina
Ora puoi scorrere tutte le pagine del documento e regolare il contenuto di ciascuna pagina in base alle dimensioni della casella del supporto. Nell'esempio fornito, regoliamo la larghezza della pagina per renderla in modalità orizzontale (landscape) mantenendo la stessa altezza. La nuova larghezza viene calcolata in base alle proporzioni della casella del supporto.

```csharp
foreach(Page page in doc.Pages)
{
     Rectangle r = page.MediaBox;
     double newHeight = r.Height;
     double newWidth = r.Height * r.Height / r.Width;
}
```

### Esempio di codice sorgente per Fit Page Contents utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Rectangle r = page.MediaBox;
	// Nuova altezza uguale
	double newHeight = r.Height;
	// La nuova larghezza viene espansa proporzionalmente per rendere l'orientamento orizzontale
	// (supponiamo che l'orientamento precedente sia verticale)
	double newWidth = r.Height * r.Height / r.Width;
}          

```

## Conclusione
In questo tutorial, abbiamo imparato come regolare il contenuto della pagina PDF utilizzando Aspose.PDF per .NET. Seguendo i passaggi descritti sopra, puoi facilmente implementare questa funzionalità nei tuoi progetti. Sentiti libero di esplorare ulteriormente la documentazione di Aspose.PDF per scoprire altre utili funzionalità per lavorare con i file PDF.
