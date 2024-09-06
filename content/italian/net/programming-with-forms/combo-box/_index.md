---
title: Casella combinata
linktitle: Casella combinata
second_title: Riferimento API Aspose.PDF per .NET
description: Crea facilmente elenchi di caselle combinate nei tuoi documenti PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-forms/combo-box/
---
In questo tutorial, ti mostreremo come creare un elenco di caselle combinate usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Fase 1: Preparazione

Per prima cosa, assicurati di aver importato le librerie necessarie e di aver impostato il percorso alla directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un oggetto documento

Crea un oggetto Documento per contenere il modulo PDF:

```csharp
Document doc = new Document();
```

## Passaggio 3: aggiungere una pagina

Aggiungere una pagina al documento:

```csharp
doc.Pages.Add();
```

## Passaggio 4: creare un'istanza di un oggetto ComboBoxField

Creare un oggetto ComboBoxField con le dimensioni desiderate:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Passaggio 5: aggiungere opzioni all'elenco a discesa

Aggiungere le opzioni desiderate all'elenco a discesa:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Passaggio 6: aggiungere l'elenco delle caselle combinate al modulo

Aggiungere l'oggetto ComboBoxField alla raccolta Campi modulo documento:

```csharp
doc.Form.Add(combo);
```

## Passaggio 7: Salvare il documento

Salva il documento PDF:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Combo Box utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crea oggetto Documento
	Document doc = new Document();
	// Aggiungi pagina all'oggetto documento
	doc.Pages.Add();
	// Crea un'istanza dell'oggetto Campo ComboBox
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Aggiungi opzione a ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Aggiungere un oggetto casella combinata alla raccolta di campi del modulo dell'oggetto documento
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

In questo tutorial, abbiamo imparato come creare un elenco di caselle combinate usando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente aggiungere un elenco di caselle combinate ai tuoi documenti PDF usando Aspose.PDF.

### Domande frequenti

#### D: Posso personalizzare l'aspetto dell'elenco delle caselle combinate utilizzando Aspose.PDF per .NET?

R: Sì, puoi personalizzare l'aspetto dell'elenco delle caselle combinate utilizzando Aspose.PDF per .NET. Puoi impostare proprietà come dimensione del carattere, colore, colore di sfondo, stile del bordo e altro ancora per adattarlo all'aspetto desiderato.

#### D: Posso impostare le opzioni selezionate predefinite nell'elenco della casella combinata?

 A: Sì, puoi impostare le opzioni selezionate predefinite nell'elenco della casella combinata utilizzando Aspose.PDF per .NET. Puoi utilizzare`Selected` proprietà del`ComboBoxField` oggetto per contrassegnare una o più opzioni come selezionate per impostazione predefinita.

#### D: Come posso recuperare il valore selezionato dall'elenco della casella combinata dopo che l'utente ha effettuato una selezione?

 A: Puoi recuperare il valore selezionato dall'elenco della casella combinata utilizzando Aspose.PDF per .NET. Dopo che l'utente ha effettuato una selezione, puoi accedere a`Value` proprietà del`ComboBoxField`oggetto per ottenere il valore selezionato.

#### D: È possibile aggiungere gestori di eventi o azioni all'elenco della casella combinata?

 R: Sì, Aspose.PDF per .NET consente di aggiungere gestori di eventi o azioni all'elenco delle caselle combinate. È possibile associare azioni JavaScript, come`OnValueChanged`, all'elenco della casella combinata per eseguire azioni specifiche quando l'utente seleziona un'opzione.

#### D: Posso aggiungere descrizioni o suggerimenti alle opzioni nell'elenco della casella combinata?

 A: Sì, puoi aggiungere suggerimenti o descrizioni alle opzioni nell'elenco della casella combinata utilizzando Aspose.PDF per .NET. Puoi impostare`AlternateName` proprietà di ciascuna opzione per fornire un suggerimento o una descrizione che verrà visualizzata quando l'utente passa il mouse sull'opzione.