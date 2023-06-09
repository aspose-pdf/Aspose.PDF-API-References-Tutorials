---
title: Pulsanti Radio Orizzontalmente E Verticalmente
linktitle: Pulsanti Radio Orizzontalmente E Verticalmente
second_title: Aspose.PDF per riferimento API .NET
description: Crea facilmente pulsanti di opzione orizzontali e verticali nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 180
url: /it/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---

In questo tutorial, ti mostreremo come creare pulsanti di opzione disposti orizzontalmente e verticalmente in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e imposta il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento

Carica il documento PDF esistente:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Passaggio 3: personalizza le opzioni del pulsante di opzione

Personalizza le opzioni del pulsante di opzione impostando le seguenti proprietà:

```csharp
formEditor. RadioGap = 4; // Distanza tra due opzioni del pulsante di opzione
formEditor. RadioHoriz = true; // Disposizione orizzontale dei pulsanti di opzione
formEditor.RadioButtonItemSize = 20; // Dimensioni dei pulsanti di opzione
formEditor.Facade.BorderWidth = 1; // Larghezza del bordo del pulsante di opzione
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Colore del bordo del pulsante di opzione
```

## Passaggio 4: aggiungi pulsanti di opzione orizzontali

Aggiungi pulsanti radio disposti orizzontalmente specificando le opzioni e la posizione del campo:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Passaggio 5: aggiungi pulsanti di opzione verticali

Aggiungi pulsanti radio disposti verticalmente specificando le opzioni e la posizione del campo:

```csharp
formEditor. RadioHoriz = false; // Disposizione verticale dei pulsanti di opzione
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Passaggio 6: salvare il documento

Salva il documento PDF modificato:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Esempio di codice sorgente per i pulsanti di opzione orizzontali e verticali utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il documento precedentemente salvato
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap è la distanza tra due opzioni di pulsanti di opzione.
	formEditor.RadioGap = 4;
	// Aggiungi pulsante di opzione orizzontale
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize se la dimensione dell'elemento del pulsante di opzione.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Aggiungi un altro pulsante di opzione situato verticalmente
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Salva il documento PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come creare pulsanti di opzione disposti orizzontalmente e verticalmente in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi personalizzare facilmente il layout dei pulsanti di opzione e aggiungerli ai tuoi documenti PDF utilizzando Aspose.PDF.