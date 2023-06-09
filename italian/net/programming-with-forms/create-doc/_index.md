---
title: Crea documento
linktitle: Crea documento
second_title: Aspose.PDF per riferimento API .NET
description: Crea facilmente un documento con pulsanti di opzione utilizzando Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-forms/create-doc/
---

In questo tutorial, ti mostreremo come creare un documento con pulsanti di opzione utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

##Fase 1: Preparazione

Innanzitutto, assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un nuovo documento

Crea un nuovo oggetto Document per contenere il documento PDF:

```csharp
Document doc = new Document();
```

## Passaggio 3: aggiungi una pagina

Aggiungi una nuova pagina al documento:

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 4: aggiungi un campo pulsante di opzione

Crea un campo pulsante di opzione e impostane la posizione e le dimensioni:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Passaggio 5: aggiungi le opzioni del pulsante di opzione

Aggiungi le opzioni desiderate al campo del pulsante di opzione. È possibile impostare le coordinate e le dimensioni di ciascuna opzione secondo necessità:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Passaggio 6: aggiungi il campo del pulsante di opzione al modulo

Aggiungi il campo del pulsante di opzione alla raccolta Campi modulo documento:

```csharp
doc.Form.Add(field);
```

## Passaggio 7: salvare il documento

Salva il documento PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Crea documento utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crea un nuovo documento
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Aggiungi il campo del pulsante di opzione
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Aggiungi le opzioni del pulsante di opzione. si prega di notare che queste opzioni sono situate
	// Né in orizzontale né in verticale.
	// Puoi provare a impostare qualsiasi coordinata (e persino dimensione) per loro.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Salva il documento PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come creare un documento con pulsanti di opzione utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente aggiungere pulsanti di opzione ai tuoi documenti PDF utilizzando Aspose.PDF.