---
title: Modifica campo modulo
linktitle: Modifica campo modulo
second_title: Aspose.PDF per riferimento API .NET
description: Modifica facilmente i campi modulo nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 190
url: /it/net/programming-with-forms/modify-form-field/
---

In questo tutorial, ti mostreremo come modificare un campo modulo in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e imposta il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento

Carica il documento PDF esistente:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## Passaggio 3: ottieni il campo del modulo

Ottieni il campo del modulo che desideri modificare:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Passaggio 4: modificare il valore del campo

Modifica il valore del campo del modulo:

```csharp
textBoxField.Value = "New Value";
```

## Passaggio 5: modificare le proprietà del campo

Modificare le proprietà aggiuntive del campo modulo in base alle esigenze. Ad esempio, puoi renderlo di sola lettura:

```csharp
textBoxField.ReadOnly = true;
```

## Passaggio 6: salvare il documento modificato

Salva il documento PDF modificato:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Modifica campo modulo utilizzando Aspose.Words per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// Prendi un campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modifica il valore del campo
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// Salva documento aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come modificare un campo modulo in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente navigare in un campo specifico, modificarne il valore e regolarne le proprietà secondo necessità.