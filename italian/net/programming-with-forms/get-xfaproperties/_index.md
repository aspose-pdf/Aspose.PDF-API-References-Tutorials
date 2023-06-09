---
title: Ottieni XFAProperties
linktitle: Ottieni XFAProperties
second_title: Aspose.PDF per riferimento API .NET
description: Ottieni facilmente le proprietà XFA dei campi modulo nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 160
url: /it/net/programming-with-forms/get-xfaproperties/
---

In questo tutorial, ti mostreremo come ottenere le proprietà XFA dei campi modulo in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e imposta il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: carica il modulo XFA

Carica il modulo XFA dal documento PDF:

```csharp
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
```

## Passaggio 3: ottieni i nomi dei campi

Ottieni i nomi dei campi XFA:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## Passaggio 4: impostare i valori dei campi

Imposta i valori per i campi XFA:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## Passaggio 5: ottieni la posizione dei campi

Ottieni la posizione dei campi XFA:

```csharp
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
```

## Passaggio 6: salvare il documento aggiornato

Salva il documento PDF aggiornato:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Ottieni XFAProperties utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il modulo XFA
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
string[] names = doc.Form.XFA.FieldNames;
// Imposta i valori del campo
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
// Ottieni posizione sul campo
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
// Ottieni posizione sul campo
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
dataDir = dataDir + "Filled_XFA_out.pdf";
// Salva il documento aggiornato
doc.Save(dataDir);
Console.WriteLine("\nXFA fields properties retrieved successfully.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere le proprietà XFA dei campi modulo in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi estrarre facilmente le informazioni sul campo XFA, come le posizioni, dai documenti PDF utilizzando Aspose.PDF.