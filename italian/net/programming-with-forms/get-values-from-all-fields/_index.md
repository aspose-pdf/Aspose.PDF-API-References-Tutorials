---
title: Ottieni valori da tutti i campi
linktitle: Ottieni valori da tutti i campi
second_title: Aspose.PDF per riferimento API .NET
description: Ottieni facilmente i valori di tutti i campi del modulo nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 150
url: /it/net/programming-with-forms/get-values-from-all-fields/
---

In questo tutorial, ti mostreremo come ottenere i valori di tutti i campi del modulo in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e imposta il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il documento

Apri il documento PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Passaggio 3: ottenere i valori per tutti i campi

Scorri tutti i campi del modulo nel documento e ottieni i loro nomi e valori:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Esempio di codice sorgente per Ottieni valori da tutti i campi utilizzando Aspose.Words per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Ottieni valori da tutti i campi
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere i valori di tutti i campi del modulo in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi estrarre facilmente i valori di tutti i campi del modulo dai tuoi documenti PDF utilizzando Aspose.PDF.