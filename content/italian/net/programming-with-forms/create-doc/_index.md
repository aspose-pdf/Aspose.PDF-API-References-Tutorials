---
title: Crea documento
linktitle: Crea documento
second_title: Riferimento API Aspose.PDF per .NET
description: Crea facilmente un documento con pulsanti di scelta utilizzando Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-forms/create-doc/
---
In questo tutorial, ti mostreremo come creare un documento con pulsanti di scelta usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

##Passaggio 1: Preparazione

Per prima cosa, assicurati di aver importato le librerie necessarie e di aver impostato il percorso alla directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un nuovo documento

Crea un nuovo oggetto Documento per contenere il documento PDF:

```csharp
Document doc = new Document();
```

## Passaggio 3: aggiungere una pagina

Aggiungi una nuova pagina al documento:

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 4: aggiungere un campo pulsante di scelta

Crea un campo pulsante di scelta e impostane posizione e dimensione:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Passaggio 5: aggiungere le opzioni del pulsante di scelta

Aggiungi le opzioni desiderate al campo del pulsante di scelta. Puoi impostare le coordinate e la dimensione di ogni opzione come necessario:

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

## Passaggio 6: aggiungere il campo del pulsante di scelta al modulo

Aggiungere il campo del pulsante di scelta alla raccolta Campi modulo documento:

```csharp
doc.Form.Add(field);
```

## Passaggio 7: Salvare il documento

Salva il documento PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per creare un documento utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crea un nuovo documento
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Aggiungi campo pulsante di scelta
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Aggiungi opzioni del pulsante di scelta. Si prega di notare che queste opzioni sono situate
	// Né orizzontalmente né verticalmente.
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

In questo tutorial, abbiamo imparato come creare un documento con pulsanti di scelta usando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente aggiungere pulsanti di scelta ai tuoi documenti PDF usando Aspose.PDF.

### Domande frequenti

#### D: Posso personalizzare l'aspetto dei pulsanti di scelta nel documento utilizzando Aspose.PDF per .NET?

R: Sì, puoi personalizzare l'aspetto dei pulsanti di scelta nel documento usando Aspose.PDF per .NET. Puoi impostare proprietà come dimensione, colore, stile del bordo e altro per personalizzare l'aspetto dei pulsanti di scelta.

#### D: Come posso aggiungere gruppi di pulsanti di scelta con opzioni reciprocamente esclusive?

R: Per creare opzioni reciprocamente esclusive, puoi aggiungere più campi di pulsanti di scelta con lo stesso nome. Questo garantirà che quando un'opzione è selezionata, le altre opzioni con lo stesso nome saranno automaticamente deselezionate.

#### D: È possibile impostare un'opzione predefinita selezionata per i pulsanti di scelta?

A: Sì, puoi impostare un'opzione selezionata predefinita per i pulsanti di scelta utilizzando Aspose.PDF per .NET. Puoi utilizzare`Selected` proprietà del`RadioButtonOptionField` oggetto per contrassegnare un'opzione come selezionata per impostazione predefinita.

#### D: Posso aggiungere gestori di eventi ai pulsanti di scelta?

 R: Sì, puoi aggiungere gestori di eventi ai pulsanti di scelta utilizzando Aspose.PDF per .NET. Puoi associare azioni JavaScript, come`OnValueChanged`, ai pulsanti di scelta per eseguire azioni specifiche quando l'utente seleziona un'opzione.

#### D: Come posso recuperare l'opzione selezionata dal gruppo dei pulsanti di scelta dopo che l'utente ha effettuato una selezione?

 A: Puoi recuperare l'opzione selezionata dal gruppo di pulsanti di scelta utilizzando Aspose.PDF per .NET. Dopo che l'utente ha effettuato una selezione, puoi accedere a`Selected` proprietà del`RadioButtonOptionField` oggetto per verificare quale opzione è selezionata.