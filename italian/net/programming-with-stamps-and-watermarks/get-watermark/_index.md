---
title: Ottieni filigrana
linktitle: Ottieni filigrana
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come estrarre filigrane dai tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-stamps-and-watermarks/get-watermark/
---
In questo tutorial, ti guideremo passo dopo passo su come ottenere una filigrana da un documento PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per scorrere gli artefatti di una pagina specifica e ottenere il tipo di filigrana, il testo e la posizione.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: caricamento del documento PDF

Il primo passaggio consiste nel caricare il documento PDF esistente nel progetto. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento PDF
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: ottenere la filigrana

Ora che hai caricato il documento PDF, puoi scorrere gli artefatti specifici della pagina per ottenere le informazioni sulla filigrana. Ecco come:

```csharp
// Sfoglia gli artefatti e ottieni il sottotipo, il testo e la posizione della filigrana
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Il codice precedente scorre tutti gli artefatti sulla prima pagina del documento PDF e visualizza il sottotipo, il testo e il rettangolo (posizione) di ogni filigrana incontrata.

### Esempio di codice sorgente per Ottieni filigrana utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Scorri e ottieni il tipo di vasca, il testo e la posizione dell'artefatto
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Conclusione

Congratulazioni! Hai imparato come ottenere informazioni sulla filigrana da un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi usare questa conoscenza per analizzare ed elaborare filigrane nei tuoi documenti PDF.
