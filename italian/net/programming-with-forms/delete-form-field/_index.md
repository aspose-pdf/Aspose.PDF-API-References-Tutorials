---
title: Elimina campo modulo
linktitle: Elimina campo modulo
second_title: Aspose.PDF per riferimento API .NET
description: Rimuovi facilmente i campi modulo indesiderati dai tuoi documenti PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-forms/delete-form-field/
---

In questo tutorial, ti mostreremo come eliminare un campo modulo utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Innanzitutto, assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: apri il documento

Apri il documento PDF esistente:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## Passaggio 3: elimina un campo specifico

Elimina un particolare campo modulo usando il suo nome:

```csharp
pdfDocument.Form.Delete("textbox1");
```

## Passaggio 4: salvare il documento modificato

Salva il documento PDF modificato:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Elimina campo modulo utilizzando Aspose.Words per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// Elimina un campo particolare per nome
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// Salva documento modificato
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come eliminare un campo modulo utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi rimuovere facilmente i campi modulo indesiderati dai tuoi documenti PDF utilizzando Aspose.PDF.