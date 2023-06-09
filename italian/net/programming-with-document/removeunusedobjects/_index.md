---
title: Rimuovi oggetti inutilizzati
linktitle: Rimuovi oggetti inutilizzati
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per rimuovere oggetti inutilizzati dai documenti PDF con questa guida dettagliata.
type: docs
weight: 260
url: /it/net/programming-with-document/removeunusedobjects/
---
Se stai cercando un modo per rimuovere oggetti inutilizzati nei tuoi documenti PDF utilizzando Aspose.PDF per .NET, sei nel posto giusto. Questa guida dettagliata ti mostrerà come utilizzare il codice sorgente C# fornito per eseguire questa operazione.

## Passaggio 1: impostare il percorso della directory

Innanzitutto, è necessario impostare il percorso della directory dei documenti sostituendo "YOUR DOCUMENT DIRECTORY" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento PDF

Successivamente, è necessario aprire il documento PDF che si desidera ottimizzare utilizzando il seguente codice:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Passaggio 3: impostare l'opzione RemoveUnusedObjects

Per rimuovere gli oggetti inutilizzati nel documento PDF, è necessario impostare l'opzione RemoveUnusedObjects su "true" come segue:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
```

## Passaggio 4: ottimizza il documento PDF utilizzando OptimizationOptions

Ora puoi ottimizzare il tuo documento PDF utilizzando il metodo OptimizeResources con le opzioni di ottimizzazione appena impostate:

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Passaggio 5: salvare il documento aggiornato

Infine, puoi salvare il documento aggiornato con il seguente codice:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

Questo è tutto! Hai rimosso con successo gli oggetti inutilizzati dal documento PDF utilizzando Aspose.PDF per .NET.

### Esempio di codice sorgente per Rimuovi oggetti inutilizzati utilizzando Aspose.PDF per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Imposta l'opzione RimuoviOggettoUsato
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
```
