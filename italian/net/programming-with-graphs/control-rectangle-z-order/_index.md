---
title: Controlla l'ordine Z del rettangolo
linktitle: Controlla l'ordine Z del rettangolo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come controllare l'ordine Z dei rettangoli in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-graphs/control-rectangle-z-order/
---

In questo tutorial, ti guideremo attraverso il seguente codice sorgente C# passo dopo passo per controllare l'ordine Z dei rettangoli usando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di configurare il tuo ambiente di sviluppo prima di iniziare. Avere anche una conoscenza di base della programmazione C#.

## Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, è necessario specificare la directory in cui si desidera salvare il file PDF risultante. Modificare la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione di un'istanza di un oggetto documento e aggiunta di una pagina

Creiamo un'istanza della classe Document e aggiungiamo una pagina a questo documento.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Passaggio 3: impostazione delle dimensioni della pagina

Impostiamo le dimensioni della pagina PDF utilizzando il metodo SetPageSize.

```csharp
page1.SetPageSize(375, 300);
```

## Passaggio 4: impostazione dei margini della pagina

Possiamo configurare i margini della pagina utilizzando le proprietà dell'oggetto PageInfo.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Passaggio 5: aggiungi rettangoli con ordine Z specificato

Creiamo e aggiungiamo rettangoli alla pagina con colori diversi e ordini Z specificati.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Passaggio 6: salvataggio del file PDF risultante

Infine, salviamo il file PDF risultante con il nome "ControlRectangleZOrder_out.pdf" nella directory specificata.

```csharp
doc1.Save(dataDir);
```
### Codice sorgente di esempio per l'ordine Z del rettangolo di controllo utilizzando Aspose.Words per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza dell'oggetto della classe Document
Document doc1 = new Document();
/// Aggiungi pagina alla raccolta di pagine di file PDF
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Imposta la dimensione della pagina PDF
page1.SetPageSize(375, 300);
// Imposta il margine sinistro per l'oggetto della pagina su 0
page1.PageInfo.Margin.Left = 0;
// Imposta il margine superiore dell'oggetto della pagina su 0
page1.PageInfo.Margin.Top = 0;
// Crea un nuovo rettangolo con Colore come Rosso, Ordine Z come 0 e determinate dimensioni
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Crea un nuovo rettangolo con Colore come blu, Ordine Z come 0 e determinate dimensioni
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Crea un nuovo rettangolo con Colore come Verde, Ordine Z come 0 e determinate dimensioni
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Salva il file PDF risultante
doc1.Save(dataDir);

```

## Conclusione

In questo tutorial, abbiamo spiegato come controllare l'ordine Z dei rettangoli utilizzando Aspose.PDF per .NET. Ora puoi utilizzare questa conoscenza per organizzare e sovrapporre con precisione i rettangoli nei tuoi file PDF.
