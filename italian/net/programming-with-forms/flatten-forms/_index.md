---
title: Appiattire le forme
linktitle: Appiattire le forme
second_title: Aspose.PDF per riferimento API .NET
description: Appiattisci facilmente i moduli nei tuoi documenti PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-forms/flatten-forms/
---

In questo tutorial, ti mostreremo come appiattire i moduli usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Innanzitutto, assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il modulo PDF di origine

Carica il modulo PDF di origine:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 3: appiattisci le forme

Innanzitutto controlla se ci sono campi modulo nel documento. In tal caso, scorrere ogni campo e applicare l'appiattimento:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Passaggio 4: salvare il documento aggiornato

Salva il documento PDF aggiornato:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Flatten Forms utilizzando Aspose.Words per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il modulo PDF di origine
Document doc = new Document(dataDir + "input.pdf");
// Appiattire le forme
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Salva il documento aggiornato
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come appiattire i moduli utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente appiattire i moduli nei tuoi documenti PDF, rendendo i campi non modificabili e unendo le annotazioni con il contenuto del documento.