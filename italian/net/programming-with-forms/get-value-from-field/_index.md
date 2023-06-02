---
title: Ottieni valore dal campo
linktitle: Ottieni valore dal campo
second_title: Aspose.PDF per riferimento API .NET
description: Ottieni facilmente il valore di un campo modulo nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 140
url: /it/net/programming-with-forms/get-value-from-field/
---

In questo tutorial, ti mostreremo come ottenere il valore di un campo modulo utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e imposta il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il documento

Apri il documento PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## Passaggio 3: ottieni il campo

Ottieni il campo del modulo desiderato (in questo esempio, stiamo usando il campo "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Passaggio 4: ottieni il valore del campo

 Ottenere il valore del campo utilizzando il`Value` proprietà:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Esempio di codice sorgente per Ottieni valore dal campo utilizzando Aspose.Words per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// Prendi un campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Ottieni il valore del campo
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere il valore di un campo modulo utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente estrarre il valore di un campo modulo specifico nei tuoi documenti PDF utilizzando Aspose.PDF.