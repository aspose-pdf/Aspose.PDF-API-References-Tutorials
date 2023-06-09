---
title: Ottieni le coordinate
linktitle: Ottieni le coordinate
second_title: Aspose.PDF per riferimento API .NET
description: Ottieni facilmente le coordinate del campo modulo nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-forms/get-coordinates/
---

In questo tutorial, ti mostreremo come ottenere le coordinate del campo modulo usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e imposta il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento di output

Carica il documento PDF di output:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Passaggio 3: trova i campi aggiunti

Trova i campi del modulo aggiunti (in questo esempio, stiamo usando i campi "Item1", "Item2" e "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Passaggio 4: visualizzare le posizioni degli elementi secondari per ciascun campo

Scorri le opzioni per ogni campo e visualizza le coordinate per ogni sottoelemento:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Esempio di codice sorgente per Ottieni coordinate utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il documento di output
	Document doc1 = new Document( dataDir + "input.pdf");
	// Trova campi aggiunti
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// E mostra le posizioni degli elementi secondari per ciascuno di essi.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere le coordinate del campo del modulo utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi recuperare facilmente le coordinate dei sottoelementi dei campi del modulo nei tuoi documenti PDF utilizzando Aspose.PDF.