---
title: Appiattisci annotazione
linktitle: Appiattisci annotazione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come appiattire le annotazioni in un documento PDF utilizzando Aspose.PDF per .NET. Conserva le annotazioni e previeni l'alterazione accidentale.
type: docs
weight: 150
url: /it/net/programming-with-document/flattenannotation/
---

Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di lavorare con i documenti PDF in modo programmatico. Una delle funzionalità che fornisce è la capacità di appiattire le annotazioni nei documenti PDF. Appiattire le annotazioni in un documento PDF significa che le annotazioni diventano parte del contenuto del documento e non possono più essere modificate o eliminate. Ciò è utile quando si desidera garantire che le annotazioni vengano conservate e non possano essere modificate accidentalmente.

In questo tutorial, discuteremo come utilizzare Aspose.PDF per .NET per appiattire le annotazioni in un documento PDF. Forniremo una guida dettagliata su come eseguire questa operazione, insieme al codice sorgente di esempio.

## Passaggio 1: creare una nuova applicazione console C#
Per iniziare, crea una nuova applicazione console C# in Visual Studio. Puoi chiamarlo come preferisci. Una volta creato il progetto, è necessario aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa lo spazio dei nomi Aspose.PDF
Aggiungi la seguente riga di codice nella parte superiore del file C# per importare lo spazio dei nomi Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Passaggio 3: apri il documento PDF
Apri il documento PDF che desideri appiattire:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Passaggio 4: appiattisci le annotazioni
Appiattire le annotazioni nel documento PDF:

```csharp
foreach (var page in pdfDocument.Pages)
{
    foreach (var annotation in page.Annotations)
    {
        annotation.Flatten();
    }
}
```

## Passaggio 5: salvare il documento aggiornato
Salva il documento aggiornato:

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per Flatten Annotation utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Appiattire le annotazioni
foreach (var page in pdfDocument.Pages)
{
	foreach (var annotation in page.Annotations)
	{
		annotation.Flatten();
	}

}
// Salva documento aggiornato
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

## Conclusione
In questo tutorial, abbiamo discusso su come appiattire le annotazioni in un documento PDF utilizzando Aspose.PDF per .NET. L'appiattimento delle annotazioni in un documento PDF è una funzione utile che garantisce che le annotazioni vengano conservate e non possano essere modificate accidentalmente. Aspose.PDF per .NET fornisce un'API semplice e facile da usare per lavorare con i documenti PDF, comprese le annotazioni di appiattimento. 

