---
title: Imposta le informazioni sul file nel file PDF
linktitle: Imposta le informazioni sul file nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per impostare le informazioni sul file nel file PDF con questa guida passo passo.
type: docs
weight: 310
url: /it/net/programming-with-document/setfileinfo/
---
Se stai lavorando su un progetto che richiede la gestione di file PDF utilizzando Aspose.PDF per .NET, una delle funzionalità che potresti voler utilizzare è la possibilità di impostare le informazioni sul file per un documento PDF. Le informazioni sul file includono vari dettagli come l'autore, la data di creazione, le parole chiave, la data di modifica, l'oggetto e il titolo. Questa guida ti guiderà attraverso il processo di impostazione delle informazioni sul file per un documento PDF utilizzando il codice sorgente C# con Aspose.PDF per .NET.

## Guida passo passo per impostare le informazioni sui file utilizzando Aspose.PDF per .NET

1. Crea un nuovo progetto C# nell'IDE di Visual Studio.
2. Aggiungi un riferimento alla libreria Aspose.PDF per .NET nel tuo progetto.
3. Crea un nuovo oggetto documento PDF fornendo il percorso del file PDF di cui desideri modificare le informazioni sul file.

## Passaggio 1: imposta il percorso della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento PDF

```csharp
// Apri documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Passaggio 3: utilizzare l'oggetto DocumentInfo per accedere alle informazioni sul file del documento PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Passaggio 4: impostare i valori delle informazioni sul file desiderati utilizzando le proprietà dell'oggetto DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Passaggio 5: salva il documento PDF aggiornato nella posizione specificata.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Passaggio 6: verificare che le informazioni sul file siano state aggiornate correttamente.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Hai impostato correttamente le informazioni sul file per un documento PDF utilizzando Aspose.PDF per .NET.

### Codice sorgente di esempio per Set File Info utilizzando Aspose.PDF per .NET


```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Specificare le informazioni sul documento
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

In conclusione, Aspose.PDF per .NET fornisce un modo semplice ed efficace per impostare le informazioni sui file per i documenti PDF. Seguendo i passaggi sopra indicati, puoi impostare facilmente i valori delle informazioni sui file desiderati per i tuoi documenti PDF utilizzando il codice sorgente C#.

### Domande frequenti per impostare le informazioni sul file nel file PDF

#### D: Posso impostare proprietà aggiuntive relative alle informazioni sui file non menzionate nell'esempio?

 R: Sì, puoi impostare ulteriori proprietà relative alle informazioni sui file utilizzando il file`DocumentInfo` oggetto in Aspose.PDF per .NET. IL`DocumentInfo`La classe fornisce varie proprietà che consentono di impostare informazioni aggiuntive come il produttore, la versione e le proprietà personalizzate.

#### D: È possibile recuperare le informazioni sul file da un documento PDF esistente?

 R: Sì, puoi recuperare le informazioni sul file da un documento PDF esistente utilizzando Aspose.PDF per .NET. Per fare questo, puoi usare il file`DocumentInfo` oggetto per accedere alle proprietà delle informazioni sul file e leggere le informazioni archiviate nel documento PDF.

#### D: L'impostazione delle informazioni sul file modifica il documento PDF originale?

R: No, l'impostazione delle informazioni sul file utilizzando Aspose.PDF per .NET non modifica il documento PDF originale. Crea invece un nuovo documento PDF con le informazioni sul file aggiornate. Il documento PDF originale rimane invariato.