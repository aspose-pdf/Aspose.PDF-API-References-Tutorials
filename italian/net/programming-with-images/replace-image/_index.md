---
title: Sostituisci immagine
linktitle: Sostituisci immagine
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata alla sostituzione di un'immagine in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 240
url: /it/net/programming-with-images/replace-image/
---

In questo tutorial, ti illustreremo come sostituire un'immagine in un documento PDF utilizzando Aspose.PDF per .NET. Segui questi passaggi per eseguire facilmente questa operazione.

## Passaggio 1: prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza di base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarlo dal sito ufficiale di Aspose.

## Passaggio 2: caricamento del documento PDF

Per iniziare, utilizza il seguente codice per caricare il documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Apri il documento
Document pdfDocument = new Document(dataDir + "ReplaceImage.pdf");
```

Assicurati di fornire il percorso corretto al tuo documento PDF.

## Passaggio 3: sostituzione di un'immagine specifica

Per sostituire un'immagine specifica nel documento PDF, utilizzare il seguente codice:

```csharp
// Sostituisci un'immagine specifica
pdfDocument.Pages[1].Resources.Images.Replace(1, new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open));
```

In questo esempio, sostituiamo l'immagine che si trova a pagina 1 del documento PDF. Assicurati di fornire il percorso corretto alla nuova immagine che desideri utilizzare.

## Passaggio 4: salvare il file PDF aggiornato

Dopo aver eseguito la sostituzione dell'immagine, salvare il file PDF aggiornato utilizzando il seguente codice:

```csharp
dataDir = dataDir + "ReplaceImage_out.pdf";
// Salva il file PDF aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage replaced successfully.\nFile saved as: " + dataDir);
```

Assicurati di fornire il percorso e il nome file desiderati per il file PDF aggiornato.

### Esempio di codice sorgente per Sostituisci immagine utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir+ "ReplaceImage.pdf");
// Sostituisci un'immagine particolare
pdfDocument.Pages[1].Resources.Images.Replace(1, new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open));
dataDir = dataDir + "ReplaceImage_out.pdf";
// Salva il file PDF aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage replaced successfully.\nFile saved at " + dataDir); 
```

## Conclusione

Congratulazioni! Hai sostituito con successo un'immagine in un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per modificare le immagini nei file PDF.