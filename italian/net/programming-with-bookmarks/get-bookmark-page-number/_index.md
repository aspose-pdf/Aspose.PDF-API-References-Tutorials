---
title: Ottieni il numero di pagina del segnalibro
linktitle: Ottieni il numero di pagina del segnalibro
second_title: Aspose.PDF per riferimento API .NET
description: Ottieni facilmente i numeri di pagina dei segnalibri dai tuoi file PDF con Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-bookmarks/get-bookmark-page-number/
---

Il recupero dei numeri di pagina associati ai segnalibri in un documento PDF può essere utile per la navigazione. Con Aspose.PDF per .NET, puoi facilmente ottenere il numero di pagina dei segnalibri seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf.Facades;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF da cui si desidera estrarre i numeri di pagina dei segnalibri. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: creare l'editor dei segnalibri

 Ora creeremo un file`PdfBookmarkEditor` oggetto per manipolare i segnalibri del documento. Usa il seguente codice:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Passaggio 4: apri il file PDF

 In questo passaggio, apriamo il file PDF utilizzando il file`BindPdf` metodo dell'editor di segnalibri. Ecco il codice corrispondente:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Passaggio 5: estrarre i segnalibri

 Ora estrarremo i segnalibri dal documento utilizzando il file`ExtractBookmarks` metodo dell'editor di segnalibri. Ecco il codice corrispondente:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Passaggio 6: sfoglia i segnalibri e ottieni i numeri di pagina

 Infine, scorriamo i segnalibri estratti e otteniamo i numeri di pagina associati a ciascun segnalibro utilizzando a`foreach` ciclo continuo. Ecco il codice corrispondente:

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

### Esempio di codice sorgente per Ottieni il numero di pagina del segnalibro utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea PdfBookmark Editor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Apri file PDF
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

Congratulazioni! Ora hai una guida passo passo per ottenere i numeri di pagina dei segnalibri con Aspose.PDF per .NET. È possibile utilizzare questo codice per recuperare le informazioni di navigazione associate a ciascun segnalibro nei documenti PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.