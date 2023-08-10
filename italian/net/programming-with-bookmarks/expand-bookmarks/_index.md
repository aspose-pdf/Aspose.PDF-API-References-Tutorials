---
title: Espandi Segnalibri nel file PDF
linktitle: Espandi Segnalibri nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Espandi facilmente i segnalibri nel file PDF per una migliore navigazione con Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-bookmarks/expand-bookmarks/
---
L'espansione dei segnalibri nel file PDF visualizzerà tutti i segnalibri aperti per impostazione predefinita. Con Aspose.PDF per .NET, puoi espandere facilmente i segnalibri seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF di cui si desidera espandere i segnalibri. Sostituire`"YOUR DOCUMENT DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF di cui vogliamo espandere i segnalibri utilizzando il seguente codice:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 4: impostare la modalità di visualizzazione della pagina

In questo passaggio, imposteremo la modalità di visualizzazione della pagina per mostrare i segnalibri per impostazione predefinita. Noi usiamo il`PageMode` proprietà del`doc` oggetto per impostare la modalità pagina desiderata. Ecco il codice corrispondente:

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

### Domande frequenti per espandere i segnalibri nel file PDF

#### D: Cosa sono i segnalibri in un file PDF?

R: I segnalibri in un file PDF sono ausili alla navigazione che consentono agli utenti di passare rapidamente a sezioni o pagine specifiche all'interno del documento. Forniscono un modo conveniente per accedere a diverse parti di un documento.

#### D: Perché dovrei espandere i segnalibri in un file PDF?

R: L'espansione dei segnalibri può migliorare l'esperienza dell'utente visualizzando tutti i segnalibri in uno stato espanso per impostazione predefinita. Ciò offre agli utenti una chiara panoramica della struttura del documento e consente loro di navigare facilmente tra le diverse sezioni.

#### D: Come posso importare le librerie necessarie per il mio progetto C#?

R: Per importare la libreria richiesta per il tuo progetto C#, utilizza la seguente direttiva di importazione:

```csharp
using Aspose.Pdf;
```

Questa direttiva consente di utilizzare le classi ei metodi forniti da Aspose.PDF per .NET.

#### D: Come faccio a specificare il percorso della cartella documenti?

 A: Nel codice sorgente fornito, sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della cartella contenente il file PDF con cui si desidera lavorare. Ciò garantisce che il codice possa individuare il file PDF di destinazione.

#### D: Come posso aprire un documento PDF per espandere i suoi segnalibri?

R: Per aprire un documento PDF per espandere i segnalibri, utilizzare il seguente codice:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Sostituire`"input.pdf"` con il nome effettivo del file.

#### D: Come posso impostare la modalità di visualizzazione della pagina per mostrare i segnalibri per impostazione predefinita?

R: Per impostare la modalità di visualizzazione della pagina per mostrare i segnalibri per impostazione predefinita, utilizzare il`PageMode` proprietà del`doc` oggetto:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### D: Come posso espandere tutti i segnalibri nel documento PDF?

 R: Per espandere tutti i segnalibri, scorrere ogni elemento del segnalibro nella raccolta delle strutture del documento e impostare il file`Open` proprietà a`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### D: Cosa succede se un segnalibro ha segnalibri secondari nidificati?

R: Se un segnalibro ha segnalibri secondari nidificati, l'espansione del segnalibro principale espanderà anche i segnalibri secondari, fornendo una visione completa della struttura del documento.

#### D: Come faccio a salvare il file PDF aggiornato dopo aver espanso i segnalibri?

R: Per salvare il file PDF aggiornato dopo aver espanso i segnalibri, utilizzare il seguente codice:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### D: Posso personalizzare l'aspetto dei segnalibri espansi?

A: Sebbene questo tutorial si concentri sull'espansione dei segnalibri per impostazione predefinita, puoi personalizzare l'aspetto dei segnalibri utilizzando le altre funzionalità e proprietà di Aspose.PDF.