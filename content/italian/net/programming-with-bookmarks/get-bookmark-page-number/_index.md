---
title: Ottieni il numero di pagina del segnalibro nel file PDF
linktitle: Ottieni il numero di pagina del segnalibro nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Ottieni facilmente il numero di pagina del segnalibro nel file PDF con Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-bookmarks/get-bookmark-page-number/
---
Il recupero dei numeri di pagina associati ai segnalibri nel file PDF può essere utile per la navigazione. Con Aspose.PDF per .NET, puoi facilmente ottenere il numero di pagina dei segnalibri seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la necessaria direttiva sulle importazioni:

```csharp
using Aspose.Pdf.Facades;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, devi specificare il percorso della cartella contenente il file PDF da cui desideri estrarre i numeri di pagina dei segnalibri. Sostituire`"YOUR DOCUMENT DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: crea l'editor dei segnalibri

 Ora creeremo un`PdfBookmarkEditor` oggetto per manipolare i segnalibri del documento. Utilizza il seguente codice:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Passaggio 4: apri il file PDF

 In questo passaggio, apriamo il file PDF utilizzando il file`BindPdf` metodo dell'editor dei segnalibri. Ecco il codice corrispondente:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Passaggio 5: estrai i segnalibri

 Ora estrarremo i segnalibri dal documento utilizzando il file`ExtractBookmarks` metodo dell'editor dei segnalibri. Ecco il codice corrispondente:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Passaggio 6: sfoglia i segnalibri e ottieni i numeri di pagina

 Infine, passiamo in rassegna i segnalibri estratti e otteniamo i numeri di pagina associati a ciascun segnalibro utilizzando a`foreach` ciclo continuo. Ecco il codice corrispondente:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Codice sorgente di esempio per Ottieni numero di pagina del segnalibro utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea PdfBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Apri il file PDF
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Estrai segnalibri
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per ottenere i numeri di pagina dei segnalibri con Aspose.PDF per .NET. Puoi utilizzare questo codice per recuperare le informazioni di navigazione associate a ciascun segnalibro nei tuoi documenti PDF.

Assicurati di controllare la documentazione ufficiale Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.

### Domande frequenti per ottenere il numero di pagina del segnalibro nel file PDF

#### D: Cosa sono i segnalibri in un file PDF?

R: I segnalibri in un file PDF sono aiuti alla navigazione che consentono agli utenti di passare rapidamente a sezioni o pagine specifiche all'interno del documento. Migliorano l'esperienza dell'utente fornendo scorciatoie ai contenuti pertinenti.

#### D: Perché dovrei recuperare i numeri di pagina dei segnalibri da un file PDF?

R: Il recupero dei numeri di pagina dei segnalibri aiuta gli utenti a navigare in un documento in modo più efficace, fornendo un'indicazione chiara della direzione in cui conduce ciascun segnalibro. Ciò è particolarmente utile per documenti più lunghi con più sezioni.

#### D: Come posso importare le librerie necessarie per il mio progetto C#?

R: Per importare la libreria richiesta per il tuo progetto C#, utilizza la seguente direttiva di importazione:

```csharp
using Aspose.Pdf.Facades;
```

Questa direttiva consente di utilizzare le classi e i metodi forniti da Aspose.PDF per .NET.

#### D: Come posso specificare il percorso della cartella dei documenti?

 R: Nel codice sorgente fornito, sostituisci`"YOUR DOCUMENT DIRECTORY"`con il percorso effettivo della cartella contenente il file PDF da cui si desidera estrarre i numeri di pagina dei segnalibri. Ciò garantisce che il codice possa individuare il file PDF di destinazione.

#### D: Come posso creare un editor di segnalibri?

R: Per creare un editor di segnalibri, utilizzare il seguente codice:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### D: Come posso aprire un file PDF per manipolare i segnalibri?

R: Per aprire un file PDF per estrarre le informazioni sui segnalibri, utilizzare il seguente codice:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Sostituire`"GetBookmarks.pdf"` con il nome effettivo del file.

#### D: Come posso estrarre i segnalibri dal file PDF?

 R: Per estrarre i segnalibri dal file PDF, utilizzare il file`ExtractBookmarks` metodo dell'editor dei segnalibri:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### D: Come posso recuperare e visualizzare i numeri delle pagine dei segnalibri?

 R: Passa in rassegna i segnalibri estratti utilizzando a`foreach` loop e accedi a`PageNumber` proprietà di ciascun segnalibro per recuperare e visualizzare il numero di pagina associato:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### D: Posso modificare le proprietà dei segnalibri utilizzando questo approccio?

 R: Anche se questo tutorial si concentra sul recupero dei numeri di pagina dei segnalibri, puoi modificare altre proprietà dei segnalibri utilizzando lo stesso`Bookmark`oggetto e proprietà associate.

#### D: Come posso salvare il file PDF aggiornato dopo aver estratto le informazioni sui segnalibri?

R: L'estrazione dei segnalibri non modifica il file PDF originale. Se desideri salvare eventuali modifiche, puoi farlo utilizzando altri metodi forniti da Aspose.PDF per .NET.