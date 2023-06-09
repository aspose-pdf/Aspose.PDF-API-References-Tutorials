---
title: Pulsante Radio
linktitle: Pulsante Radio
second_title: Aspose.PDF per riferimento API .NET
description: Aggiungi facilmente pulsanti di opzione ai tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 220
url: /it/net/programming-with-forms/radio-button/
---

In questo tutorial, ti mostreremo come aggiungere un pulsante di opzione in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e imposta il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creare un'istanza di un oggetto documento

Crea un'istanza di un oggetto Document per creare un nuovo documento PDF:

```csharp
Document pdfDocument = new Document();
```

## Passaggio 3: aggiungi una pagina

Aggiungere una pagina al documento PDF:

```csharp
pdfDocument.Pages.Add();
```

## Passaggio 4: creare un'istanza di un oggetto RadioButtonField

Crea un'istanza di un oggetto RadioButtonField specificando il numero di pagina come argomento:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Passaggio 5: aggiungi le opzioni del pulsante di opzione

Aggiungi le opzioni del pulsante di opzione all'oggetto RadioButtonField specificando le coordinate di ciascuna opzione con un oggetto Rectangle:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Passaggio 6: aggiungi il pulsante di opzione al modulo

Aggiungi il pulsante di opzione all'oggetto Modulo del documento:

```csharp
pdfDocument.Form.Add(radio);
```

## Passaggio 7: salva il documento PDF

Salva il documento PDF creato:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Radio Button utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crea un'istanza dell'oggetto Document
	Document pdfDocument = new Document();
	// Aggiungi una pagina al file PDF
	pdfDocument.Pages.Add();
	// Crea un oggetto RadioButtonField con il numero di pagina come argomento
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Aggiungi l'opzione del primo pulsante di opzione e specifica anche la sua origine utilizzando l'oggetto Rectangle
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Aggiungi la seconda opzione del pulsante di opzione
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Aggiungi pulsante di opzione all'oggetto modulo dell'oggetto Documento
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Salva il file PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come aggiungere un pulsante di opzione in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente creare un pulsante di opzione e posizionarlo su una pagina specifica nel tuo documento PDF.