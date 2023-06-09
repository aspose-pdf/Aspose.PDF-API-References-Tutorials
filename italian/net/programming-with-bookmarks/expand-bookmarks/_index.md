---
title: Espandi Segnalibri
linktitle: Espandi Segnalibri
second_title: Aspose.PDF per riferimento API .NET
description: Espandi facilmente i segnalibri dei tuoi file PDF per una migliore navigazione con Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-bookmarks/expand-bookmarks/
---

L'espansione dei segnalibri in un documento PDF visualizzerà tutti i segnalibri aperti per impostazione predefinita. Con Aspose.PDF per .NET, puoi espandere facilmente i segnalibri seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF di cui si desidera espandere i segnalibri. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF di cui vogliamo espandere i segnalibri utilizzando il seguente codice:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 4: impostare la modalità di visualizzazione della pagina

 In questo passaggio, imposteremo la modalità di visualizzazione della pagina per mostrare i segnalibri per impostazione predefinita. Noi usiamo il`PageMode` proprietà del`doc`oggetto per impostare la modalità pagina desiderata. Ecco il codice corrispondente:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Passaggio 5: sfoglia i segnalibri ed espandili

 Ora passeremo in rassegna ogni elemento dei segnalibri nella raccolta di segnalibri del documento e imposteremo lo stato aperto di ogni elemento su`true` per espanderli per impostazione predefinita. Ecco il codice corrispondente:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Passaggio 6: salvare il file aggiornato

 Infine, salviamo il file PDF aggiornato utilizzando l'estensione`Save` metodo del`doc` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Codice sorgente di esempio per espandere i segnalibri utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document doc = new Document(dataDir + "input.pdf");
// Imposta la modalità di visualizzazione della pagina, ad esempio mostra le miniature, a schermo intero, mostra il pannello degli allegati
doc.PageMode = PageMode.UseOutlines;
// Attraversa ogni elemento Ouline nella raccolta di contorni del file PDF
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Imposta lo stato di apertura per l'elemento del profilo
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Salva output
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo allo sviluppo di segnalibri con Aspose.PDF per .NET. Puoi usare questo codice per mostrare tutti i segnalibri predefiniti nei tuoi documenti PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.