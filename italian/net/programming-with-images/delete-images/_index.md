---
title: Elimina immagini
linktitle: Elimina immagini
second_title: Aspose.PDF per riferimento API .NET
description: Elimina facilmente le immagini da un file PDF con Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/programming-with-images/delete-images/
---

Questa guida ti guiderà passo dopo passo su come eliminare le immagini da un file PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento PDF

 In questo passaggio, apriremo il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteImages.pdf");

```

## Passaggio 3: eliminare un'immagine specifica

 In questo passaggio, elimineremo un'immagine specifica da una determinata pagina. Usa il`Delete` metodo della risorsa pagina`Images` oggetto per eliminare l'immagine. Nell'esempio seguente, eliminiamo l'immagine con indice 1 dalla prima pagina.

```csharp
pdfDocument.Pages[1].Resources.Images.Delete(1);
```

## Passaggio 4: salvare il file PDF aggiornato

 Salvare il file PDF aggiornato utilizzando il file`Save` metodo del`pdfDocument` oggetto. Specificare il percorso di output per il file PDF.

```csharp
dataDir = dataDir + "DeleteImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Elimina immagini utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
//Elimina un'immagine particolare
pdfDocument.Pages[1].Resources.Images.Delete(1);
dataDir = dataDir + "DeleteImages_out.pdf";
// Salva il file PDF aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```

## Conclusione

Congratulazioni! Hai eliminato con successo le immagini da un file PDF utilizzando Aspose.PDF per .NET. Il file PDF aggiornato viene salvato nella directory specificata. Ora puoi utilizzare questo file PDF senza le immagini eliminate.