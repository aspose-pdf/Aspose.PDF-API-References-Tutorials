---
title: Da HTML a PDF
linktitle: Da HTML a PDF
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire HTML in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/document-conversion/html-to-pdf/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file HTML in PDF utilizzando Aspose.PDF per .NET. HTML (HyperText Markup Language) è un linguaggio di markup utilizzato per strutturare e presentare contenuti web. Seguendo i passaggi seguenti, sarai in grado di convertire i file HTML in formato PDF.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: caricamento del file HTML
In questo passaggio, caricheremo il file HTML utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

HtmlLoadOptions options = new HtmlLoadOptions();
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file HTML.

## Passaggio 2: opzioni di caricamento HTML
Ora che abbiamo caricato il file HTML, possiamo specificare opzioni di caricamento specifiche. Usa il seguente codice:

```csharp
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);
```

Il codice sopra indica ad Aspose.PDF di utilizzare una strategia di caricamento personalizzata per le risorse esterne, come le immagini. È possibile personalizzare questa politica in base alle proprie esigenze.

## Passaggio 3: conversione da HTML a PDF
Dopo aver caricato il file HTML e aver specificato le opzioni di caricamento, possiamo procedere con la conversione in PDF. Usa il seguente codice:

```csharp
pdfDocument.Save("HTMLToPDF_out.pdf");
```

### Esempio di codice sorgente per HTML in PDF utilizzando Aspose.Words per .NET

```csharp
try
{
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	HtmlLoadOptions options = new HtmlLoadOptions();
	options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

	Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
	pdfDocument.Save("HTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo dopo passo. passaggio di conversione di un file HTML in PDF utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire i file HTML in formato PDF. Questa funzione può essere utile quando è necessario generare documenti PDF da contenuto HTML.

