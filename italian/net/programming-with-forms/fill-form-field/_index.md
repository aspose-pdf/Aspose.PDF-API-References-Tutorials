---
title: Compila il campo del modulo
linktitle: Compila il campo del modulo
second_title: Aspose.PDF per riferimento API .NET
description: Compila facilmente i campi dei moduli nei tuoi documenti PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-forms/fill-form-field/
---

In questo tutorial, ti mostreremo come popolare un campo modulo usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Innanzitutto, assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento

Apri il documento PDF esistente:

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## Passaggio 3: ottieni il campo

Ottieni il campo del modulo desiderato (in questo esempio, stiamo usando il campo "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Passaggio 4: modificare il valore del campo

Modificare il valore del campo con il valore desiderato:

```csharp
textBoxField.Value = "Value to fill in the field";
```

## Passaggio 5: salvare il documento aggiornato

Salva il documento PDF aggiornato:

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Fill Form Field utilizzando Aspose.Words per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
// Prendi un campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modifica il valore del campo
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come popolare un campo modulo utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi modificare facilmente i valori dei campi modulo nei tuoi documenti PDF utilizzando Aspose.PDF.