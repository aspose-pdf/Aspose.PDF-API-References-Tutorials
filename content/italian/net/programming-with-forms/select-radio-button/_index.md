---
title: Seleziona il pulsante di scelta nel documento PDF
linktitle: Seleziona il pulsante di scelta nel documento PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come selezionare un pulsante di scelta in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 250
url: /it/net/programming-with-forms/select-radio-button/
---
Ecco un tutorial dettagliato su come selezionare un pulsante di scelta utilizzando Aspose.PDF per .NET. Seguire questi passaggi:

##  Passaggio 1: Inizia definendo la directory dei tuoi documenti specificando il percorso nel`dataDir` variable.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Passaggio 2: aprire il documento PDF utilizzando`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Passaggio 3: ottenere il campo del pulsante di scelta dal modulo del documento.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Passaggio 4: specificare l'indice del pulsante di scelta da selezionare dal gruppo.

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

## Passaggio 7: Visualizza un messaggio di conferma e la posizione del file salvato.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Esempio di codice sorgente per Seleziona pulsante di scelta utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Apri documento
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Ottieni un campo
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Specificare l'indice del pulsante di scelta dal gruppo
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

In questo tutorial, abbiamo imparato come selezionare un pulsante di scelta usando Aspose.PDF per .NET. Seguendo i passaggi descritti sopra, puoi manipolare e modificare i pulsanti di scelta nei tuoi documenti PDF usando Aspose.PDF per .NET.


### Domande frequenti

#### D: Posso selezionare più pulsanti di scelta in un gruppo utilizzando Aspose.PDF per .NET?

R: No, i pulsanti di scelta in un gruppo sono progettati per essere reciprocamente esclusivi. Puoi selezionare solo un pulsante di scelta alla volta all'interno di un gruppo e selezionandone uno deselezionerai automaticamente qualsiasi pulsante di scelta selezionato in precedenza nello stesso gruppo.

#### D: Come posso recuperare il pulsante di scelta selezionato in un gruppo utilizzando Aspose.PDF per .NET?

 A: Per recuperare il pulsante di scelta selezionato in un gruppo, puoi utilizzare`Selected` proprietà del`RadioButtonField` classe. Restituirà l'indice del pulsante di scelta selezionato all'interno del gruppo.

#### D: Posso personalizzare l'aspetto del pulsante di scelta selezionato nel documento PDF?

R: Sì, puoi personalizzare l'aspetto del pulsante di scelta selezionato utilizzando Aspose.PDF per .NET. Puoi modificarne il colore, le dimensioni, lo stile del bordo e altri attributi visivi per adattarli all'aspetto desiderato.

#### D: È possibile creare nuovi gruppi di pulsanti di scelta a livello di programmazione utilizzando Aspose.PDF per .NET?

R: Sì, puoi creare nuovi gruppi di pulsanti di scelta a livello di programmazione usando Aspose.PDF per .NET. Puoi aggiungere nuovi pulsanti di scelta al modulo del documento e specificare lo stesso nome di gruppo per ogni pulsante di scelta per creare un nuovo gruppo.

#### D: Aspose.PDF per .NET supporta l'utilizzo di moduli PDF interattivi?

R: Sì, Aspose.PDF per .NET supporta pienamente il lavoro con moduli PDF interattivi, inclusi pulsanti di scelta, campi di testo, caselle di controllo e altri elementi del modulo. Puoi facilmente leggere, modificare e creare moduli PDF interattivi utilizzando la libreria.