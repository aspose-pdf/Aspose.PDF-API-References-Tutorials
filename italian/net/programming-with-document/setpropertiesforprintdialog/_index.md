---
title: Finestra di dialogo Imposta proprietà per la stampa
linktitle: Finestra di dialogo Imposta proprietà per la stampa
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come impostare le proprietà per la finestra di dialogo di stampa in Aspose.PDF per .NET utilizzando la guida dettagliata.
type: docs
weight: 320
url: /it/net/programming-with-document/setpropertiesforprintdialog/
---
ecco una guida dettagliata per l'impostazione delle proprietà per la finestra di dialogo di stampa utilizzando Aspose.PDF per .NET:


## Passaggio 1: definire la directory in cui si trova il documento PDF:

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";
```
   
##  Passaggio 2: creare una nuova istanza di`Document` class:

```csharp
using (Document doc = new Document())
{
  // Codice qui
}
```
   
## Passaggio 3: aggiungi una nuova pagina al documento:

```csharp
doc.Pages.Add();
```
   
##  Passaggio 4: impostare la proprietà duplex su`DuplexFlipLongEdge`:

```csharp
doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
```
   
## Passaggio 5: salvare il documento con il nome file e il formato specificati:

```csharp
doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
```

### Esempio di codice sorgente per Imposta proprietà per la finestra di dialogo di stampa utilizzando Aspose.PDF per .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document doc = new Document())
{
	doc.Pages.Add();
	doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
	doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
}
```

## Conclusione

Aspose.PDF per .NET semplifica l'impostazione delle proprietà per la finestra di dialogo di stampa nei file PDF. Seguendo la guida dettagliata sopra, puoi ottimizzare rapidamente i tuoi file PDF per la stampa.