---
title: Consenti Riutilizzo del contenuto della pagina
linktitle: Consenti Riutilizzo del contenuto della pagina
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come ottimizzare i PDF abilitando la funzione "Consenti riutilizzo del contenuto della pagina" utilizzando Aspose.PDF per .NET. Riduci le dimensioni del file e migliora le prestazioni.
type: docs
weight: 50
url: /it/net/programming-with-document/allowresusepagecontent/
---

In questo tutorial, spiegheremo come abilitare la funzione "Consenti riutilizzo del contenuto della pagina" utilizzando Aspose.PDF per .NET. Questa funzione ottimizza il documento PDF riutilizzando il contenuto della pagina, riducendo le dimensioni del file e migliorando le prestazioni. Segui la guida dettagliata di seguito:

## Passaggio 1: caricare il documento PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Passaggio 2: impostare l'opzione AllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Passaggio 3: ottimizza il documento PDF

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Passaggio 4: salvare il documento aggiornato

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Passaggio 5: verifica la riduzione delle dimensioni del file

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Congratulazioni! Hai consentito con successo il riutilizzo del contenuto della pagina nel tuo documento PDF.

### Codice sorgente di esempio per Consentire il riutilizzo del contenuto della pagina utilizzando Aspose.PDF per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Impostare l'opzione AllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

// Ottimizza il documento PDF utilizzando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

// Salva documento aggiornato
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Ora puoi ottimizzare efficacemente i tuoi documenti PDF consentendo il riutilizzo del contenuto della pagina.
