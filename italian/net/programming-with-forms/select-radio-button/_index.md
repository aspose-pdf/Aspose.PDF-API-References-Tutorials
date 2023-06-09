---
title: Seleziona il pulsante di opzione
linktitle: Seleziona il pulsante di opzione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come selezionare un pulsante di opzione in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 250
url: /it/net/programming-with-forms/select-radio-button/
---

Ecco un tutorial dettagliato su come selezionare un pulsante di opzione utilizzando Aspose.PDF per .NET. Segui questi passi:

##  Passaggio 1: Inizia definendo la directory dei tuoi documenti specificando il percorso nel file`dataDir` variable.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Passaggio 2: aprire il documento PDF utilizzando il file`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Passaggio 3: ottieni il campo del pulsante di opzione dal modulo del documento.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Passaggio 4: specificare l'indice del pulsante di opzione da selezionare dal gruppo.

```csharp
radioField. Selected = 2;
```

## Passaggio 5: impostare il percorso di output per il file PDF modificato.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Passaggio 6: salvare il file PDF modificato.

```csharp
pdfDocument.Save(dataDir);
```

## Passaggio 7: visualizza un messaggio di conferma e la posizione del file salvato.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Esempio di codice sorgente per Select Radio Button utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Apri documento
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Prendi un campo
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Specificare l'indice del pulsante di opzione dal gruppo
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Salva il file PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come selezionare un pulsante di opzione utilizzando Aspose.PDF per .NET. Seguendo i passaggi sopra descritti, è possibile manipolare e modificare i pulsanti di opzione nei documenti PDF utilizzando Aspose.PDF per .NET.