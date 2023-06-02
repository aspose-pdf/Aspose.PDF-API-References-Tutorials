---
title: Imposta data di scadenza
linktitle: Imposta data di scadenza
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come impostare la data di scadenza nei documenti PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.
type: docs
weight: 300
url: /it/net/programming-with-document/setexpirydate/
---
Aspose.PDF per .NET è una potente libreria che offre varie funzionalità per lavorare con i file PDF. Una di queste funzionalità è la possibilità di impostare una data di scadenza per un documento PDF. In questo tutorial, ti guideremo attraverso il processo di impostazione di una data di scadenza per un documento PDF utilizzando Aspose.PDF per .NET. 

## Passaggio 1: impostare il percorso della directory dei documenti

Prima di iniziare, dobbiamo impostare il percorso della directory in cui si trova il nostro documento PDF. Memorizzeremo questo percorso in una variabile chiamata "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creazione di un nuovo documento PDF

Per creare un nuovo documento PDF, dobbiamo istanziare un nuovo file`Aspose.Pdf.Document` oggetto. Possiamo farlo usando il seguente codice:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Passaggio 3: aggiunta di una nuova pagina al documento PDF

Una volta creato il documento PDF, possiamo aggiungervi una nuova pagina. Possiamo farlo usando il seguente codice:

```csharp
doc.Pages.Add();
```

## Passaggio 4: aggiunta di testo al documento PDF

 Dopo aver aggiunto una pagina al documento PDF, possiamo aggiungere del testo usando il file`Paragraphs` collezione. Possiamo farlo usando il seguente codice:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Passaggio 5: impostazione della data di scadenza del PDF tramite JavaScript

Per impostare la data di scadenza del PDF, dobbiamo creare un oggetto JavaScript. Possiamo farlo usando il seguente codice:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Imposta JavaScript come azione di apertura PDF
doc.OpenAction = javaScript;
```

In questo codice, stiamo impostando la data di scadenza a maggio 2017.

## Passaggio 6: salva il file PDF

 Dopo aver impostato la data di scadenza, è necessario salvare il file PDF. Per fare questo, puoi usare il`Save` metodo del`Document` oggetto e passare il percorso in cui si desidera salvare il file PDF aggiornato.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Salva documento PDF
doc.Save(dataDir);
```

### Codice sorgente di esempio per Imposta data di scadenza utilizzando Aspose.PDF per .NET

Ecco il codice sorgente di esempio completo per l'impostazione della data di scadenza utilizzando Aspose.PDF per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza dell'oggetto Document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Aggiungi pagine alla raccolta di pagine di file PDF
doc.Pages.Add();
// Aggiungi frammento di testo alla raccolta di paragrafi dell'oggetto pagina
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Crea un oggetto JavaScript per impostare la data di scadenza del PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Imposta JavaScript come azione di apertura PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Salva documento PDF
doc.Save(dataDir);
```
