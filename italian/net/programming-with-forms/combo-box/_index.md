---
title: Casella combinata
linktitle: Casella combinata
second_title: Aspose.PDF per riferimento API .NET
description: Crea facilmente un elenco di caselle combinate nei tuoi documenti PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-forms/combo-box/
---

In questo tutorial, ti mostreremo come creare un elenco di caselle combinate utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Innanzitutto, assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un oggetto documento

Crea un oggetto Document per contenere il modulo PDF:

```csharp
Document doc = new Document();
```

## Passaggio 3: aggiungi una pagina

Aggiungi una pagina al documento:

```csharp
doc.Pages.Add();
```

## Passaggio 4: creare un'istanza di un oggetto ComboBoxField

Crea un'istanza di un oggetto ComboBoxField con le dimensioni desiderate:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Passaggio 5: aggiungi le opzioni all'elenco a discesa

Aggiungere le opzioni desiderate all'elenco a discesa:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Passaggio 6: aggiungere l'elenco della casella combinata al modulo

Aggiungere l'oggetto ComboBoxField alla raccolta Campi modulo documento:

```csharp
doc.Form.Add(combo);
```

## Passaggio 7: salvare il documento

Salva il documento PDF:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Combo Box utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crea oggetto documento
	Document doc = new Document();
	// Aggiungi pagina all'oggetto documento
	doc.Pages.Add();
	// Crea un'istanza dell'oggetto ComboBox Field
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Aggiungi opzione a ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Aggiungi oggetto casella combinata alla raccolta di campi modulo dell'oggetto documento
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Salva il documento PDF
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come creare un elenco di caselle combinate utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi aggiungere facilmente un elenco di caselle combinate ai tuoi documenti PDF utilizzando Aspose.PDF.