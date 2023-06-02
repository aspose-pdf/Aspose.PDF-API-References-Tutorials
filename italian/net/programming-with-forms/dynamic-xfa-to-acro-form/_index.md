---
title: Da XFA dinamico a modulo Acro
linktitle: Da XFA dinamico a modulo Acro
second_title: Aspose.PDF per riferimento API .NET
description: Converti facilmente i moduli XFA dinamici in moduli AcroForm standard con Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/programming-with-forms/dynamic-xfa-to-acro-form/
---

In questo tutorial, ti mostreremo come convertire un XFA in un modulo dinamico in un AcroForm utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Innanzitutto, assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il modulo XFA dinamico

Carica il modulo XFA dinamico:

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## Passaggio 3: imposta il tipo di modulo come AcroForm standard

Imposta il tipo di modulo come AcroForm standard:

```csharp
document.Form.Type = FormType.Standard;
```

## Passaggio 4: salvare il PDF risultante

Salva il PDF risultante:

```csharp
dataDir = dataDir + "Standard_AcroForm_out.pdf";
document. Save(dataDir);
```

### Esempio di codice sorgente per Dynamic XFA To Acro Form utilizzando Aspose.Words per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica modulo XFA dinamico
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// Imposta il tipo di campi del modulo come AcroForm standard
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// Salva il PDF risultante
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come convertire un modulo dinamico XFA in un modulo AcroForm standard utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi convertire facilmente i tuoi moduli XFATo dinamici in AcroForms per un uso più comune.