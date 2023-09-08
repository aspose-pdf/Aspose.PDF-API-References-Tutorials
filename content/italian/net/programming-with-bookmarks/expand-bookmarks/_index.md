---
title: Espandi Segnalibri nel file PDF
linktitle: Espandi Segnalibri nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Espandi facilmente i segnalibri nel file PDF per una migliore navigazione con Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-bookmarks/expand-bookmarks/
---
L'espansione dei segnalibri nel file PDF visualizzerà tutti i segnalibri aperti per impostazione predefinita. Con Aspose.PDF per .NET, puoi facilmente espandere i segnalibri seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la necessaria direttiva sulle importazioni:

```csharp
using Aspose.Pdf;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, devi specificare il percorso della cartella contenente il file PDF di cui desideri espandere i segnalibri. Sostituire`"YOUR DOCUMENT DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF di cui vogliamo espandere i segnalibri utilizzando il seguente codice:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 4: impostare la modalità di visualizzazione della pagina

In questo passaggio, imposteremo la modalità di visualizzazione della pagina per mostrare i segnalibri per impostazione predefinita. Noi usiamo il`PageMode` proprietà del`doc` oggetto per impostare la modalità di pagina desiderata. Ecco il codice corrispondente:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Passaggio 5: sfoglia i segnalibri ed espandili

 Ora scorreremo ogni elemento segnalibro nella raccolta di segnalibri del documento e imposteremo lo stato aperto di ciascun elemento su`true` per espanderli per impostazione predefinita. Ecco il codice corrispondente:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Passaggio 6: salva il file aggiornato

 Infine, salviamo il file PDF aggiornato utilizzando il file`Save` metodo del`doc` oggetto. Ecco il codice corrispondente:

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
// Imposta la modalità di visualizzazione della pagina, ad esempio mostra miniature, schermo intero, mostra pannello allegati
doc.PageMode = PageMode.UseOutlines;
// Attraversa ogni elemento Ouline nella raccolta di contorni del file PDF
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Imposta lo stato aperto per l'elemento del contorno
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Salva l'output
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per sviluppare segnalibri con Aspose.PDF per .NET. Puoi utilizzare questo codice per mostrare tutti i segnalibri predefiniti nei tuoi documenti PDF.

Assicurati di controllare la documentazione ufficiale Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.

### Domande frequenti per espandere i segnalibri nel file PDF

#### D: Cosa sono i segnalibri in un file PDF?

R: I segnalibri in un file PDF sono aiuti alla navigazione che consentono agli utenti di passare rapidamente a sezioni o pagine specifiche all'interno del documento. Forniscono un modo conveniente per accedere a diverse parti di un documento.

#### D: Perché dovrei espandere i segnalibri in un file PDF?

R: L'espansione dei segnalibri può migliorare l'esperienza dell'utente visualizzando tutti i segnalibri in uno stato espanso per impostazione predefinita. Ciò offre agli utenti una chiara panoramica della struttura del documento e consente loro di navigare facilmente tra le diverse sezioni.

#### D: Come posso importare le librerie necessarie per il mio progetto C#?

R: Per importare la libreria richiesta per il tuo progetto C#, utilizza la seguente direttiva di importazione:

```csharp
using Aspose.Pdf;
```

Questa direttiva consente di utilizzare le classi e i metodi forniti da Aspose.PDF per .NET.

#### D: Come posso specificare il percorso della cartella dei documenti?

 R: Nel codice sorgente fornito, sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della cartella contenente il file PDF con cui desideri lavorare. Ciò garantisce che il codice possa individuare il file PDF di destinazione.

#### D: Come posso aprire un documento PDF per espandere i suoi segnalibri?

R: Per aprire un documento PDF per espandere i segnalibri, utilizzare il seguente codice:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Sostituire`"input.pdf"` con il nome effettivo del file.

#### D: Come posso impostare la modalità di visualizzazione della pagina per mostrare i segnalibri per impostazione predefinita?

R: Per impostare la modalità di visualizzazione della pagina in modo che mostri i segnalibri per impostazione predefinita, utilizzare il file`PageMode` proprietà del`doc` oggetto:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### D: Come posso espandere tutti i segnalibri nel documento PDF?

 R: Per espandere tutti i segnalibri, scorrere ciascun elemento segnalibro nella raccolta delle strutture del documento e impostare il file`Open` proprietà a`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### D: Cosa succede se un segnalibro contiene segnalibri secondari nidificati?

R: Se un segnalibro ha segnalibri secondari nidificati, l'espansione del segnalibro principale espanderà anche i suoi segnalibri secondari, fornendo una visualizzazione completa della struttura del documento.

#### D: Come posso salvare il file PDF aggiornato dopo aver espanso i segnalibri?

R: Per salvare il file PDF aggiornato dopo aver espanso i segnalibri, utilizzare il seguente codice:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### D: Posso personalizzare l'aspetto dei segnalibri espansi?

R: Sebbene questo tutorial si concentri sull'espansione dei segnalibri per impostazione predefinita, puoi personalizzare l'aspetto dei segnalibri utilizzando le altre funzionalità e proprietà di Aspose.PDF.