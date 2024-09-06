---
title: Imposta le informazioni del file nel file PDF
linktitle: Imposta le informazioni del file nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come utilizzare Aspose.PDF per .NET per impostare le informazioni sui file in un file PDF con questa guida dettagliata.
type: docs
weight: 310
url: /it/net/programming-with-document/setfileinfo/
---
Se stai lavorando a un progetto che richiede la gestione di file PDF tramite Aspose.PDF per .NET, una delle funzionalità che potresti voler utilizzare è la possibilità di impostare le informazioni sui file per un documento PDF. Le informazioni sui file includono vari dettagli come autore, data di creazione, parole chiave, data di modifica, oggetto e titolo. Questa guida ti guiderà attraverso il processo di impostazione delle informazioni sui file per un documento PDF tramite codice sorgente C# con Aspose.PDF per .NET.

## Guida passo passo per impostare le informazioni del file utilizzando Aspose.PDF per .NET

1. Crea un nuovo progetto C# nell'IDE di Visual Studio.
2. Aggiungi un riferimento alla libreria Aspose.PDF per .NET nel tuo progetto.
3. Crea un nuovo oggetto documento PDF specificando il percorso al file PDF di cui desideri modificare le informazioni.

## Passaggio 1: impostare il percorso della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: aprire il documento PDF

```csharp
// Apri documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Passaggio 3: utilizzare l'oggetto DocumentInfo per accedere alle informazioni del file del documento PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Passaggio 4: impostare i valori desiderati delle informazioni sul file utilizzando le proprietà dell'oggetto DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Passaggio 5: salvare il documento PDF aggiornato nella posizione specificata.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Passaggio 6: verificare che le informazioni del file siano state aggiornate correttamente.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Hai impostato correttamente le informazioni del file per un documento PDF utilizzando Aspose.PDF per .NET.

### Esempio di codice sorgente per Set File Info utilizzando Aspose.PDF per .NET


```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Specificare le informazioni del documento
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Salva il documento di output
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Conclusione

In conclusione, Aspose.PDF per .NET fornisce un modo semplice ed efficace per impostare le informazioni sui file per i documenti PDF. Seguendo i passaggi sopra menzionati, puoi facilmente impostare i valori desiderati delle informazioni sui file per i tuoi documenti PDF utilizzando il codice sorgente C#.

### Domande frequenti per le informazioni sui file impostati in un file PDF

#### D: Posso impostare ulteriori proprietà di informazioni sul file non menzionate nell'esempio?

 A: Sì, puoi impostare proprietà aggiuntive delle informazioni sul file utilizzando`DocumentInfo` oggetto in Aspose.PDF per .NET. L'`DocumentInfo`La classe fornisce varie proprietà che consentono di impostare informazioni aggiuntive, come il produttore, la versione e le proprietà personalizzate.

#### D: È possibile recuperare le informazioni di un file da un documento PDF esistente?

 A: Sì, puoi recuperare le informazioni del file da un documento PDF esistente utilizzando Aspose.PDF per .NET. Per fare ciò, puoi utilizzare`DocumentInfo` oggetto per accedere alle proprietà delle informazioni del file e leggere le informazioni memorizzate nel documento PDF.

#### D: L'impostazione delle informazioni sul file modifica il documento PDF originale?

R: No, l'impostazione delle informazioni del file tramite Aspose.PDF per .NET non modifica il documento PDF originale. Invece, crea un nuovo documento PDF con le informazioni del file aggiornate. Il documento PDF originale rimane invariato.