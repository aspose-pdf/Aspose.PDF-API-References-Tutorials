---
title: Ottieni campi dalla regione
linktitle: Ottieni campi dalla regione
second_title: Aspose.PDF per riferimento API .NET
description: Ottieni facilmente campi da una regione specifica nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 130
url: /it/net/programming-with-forms/get-fields-from-region/
---

In questo tutorial, ti mostreremo come ottenere i campi di una regione specifica in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e imposta il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il file PDF

Apri il file PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Passaggio 3: creare un oggetto rettangolo per delimitare la regione

Crea un oggetto rettangolo per delimitare la regione in cui desideri ottenere i campi:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Passaggio 4: ottenere il modulo PDF

Ottieni il modulo PDF del documento:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Passaggio 5: ottieni i campi nella regione rettangolare

Ottieni i campi situati nell'area rettangolare specificata:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Passaggio 6: visualizzare i nomi e i valori dei campi

Scorri i campi risultanti e visualizza i loro nomi e valori:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Esempio di codice sorgente per Ottieni campi dalla regione utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri file pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Crea un oggetto rettangolo per ottenere campi in quell'area
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Ottieni il modulo PDF
Aspose.Pdf.Forms.Form form = doc.Form;
//Ottieni campi nell'area rettangolare
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Visualizza i nomi e i valori dei campi
foreach (Field field in fields)
{
	// Visualizza le proprietà del posizionamento dell'immagine per tutti i posizionamenti
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere i campi di una regione specifica in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente estrarre i campi situati in una data area rettangolare del tuo documento PDF usando Aspose.PDF.