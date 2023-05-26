---
title: Conversione da RGB a scala di grigi
linktitle: Conversione da RGB a scala di grigi
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come convertire i PDF da RGB a scala di grigi utilizzando Aspose.PDF per .NET. Migliora la qualità di stampa e riduci le dimensioni del file.
type: docs
weight: 60
url: /it/net/programming-with-document/convertfromrgbtograyscale/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un documento PDF dallo spazio colore RGB alla scala di grigi utilizzando Aspose.PDF per .NET. Questa conversione può essere utile per vari scopi, come la riduzione delle dimensioni del file o la preparazione dei documenti per la stampa. Segui la guida dettagliata di seguito:

## Passaggio 1: carica il file PDF di origine

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document document = new Document(dataDir + "input.pdf"))
{
    // Il tuo codice qui...
}
```

## Passaggio 2: imposta la strategia di conversione

```csharp
Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();
```

## Passaggio 3: converti ogni pagina in scala di grigi

```csharp
for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
{
    Page page = document.Pages[idxPage];
    strategy.Convert(page);
}
```

## Passaggio 4: salvare il file risultante

```csharp
document.Save(dataDir + "Test-gray_out.pdf");
```

Congratulazioni! Hai convertito con successo il documento PDF da RGB a scala di grigi utilizzando Aspose.PDF per .NET.

### Esempio di codice sorgente per Converti da RGB a scala di grigi utilizzando Aspose.PDF per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica il file PDF di origine
using (Document document = new Document(dataDir + "input.pdf"))
{
    Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();

    for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
    {
        Page page = document.Pages[idxPage];
        strategy.Convert(page);
    }

    document.Save(dataDir + "Test-gray_out.pdf");
}
```

Ora puoi convertire facilmente i tuoi documenti PDF da RGB a Scala di grigi utilizzando Aspose.PDF per .NET.

