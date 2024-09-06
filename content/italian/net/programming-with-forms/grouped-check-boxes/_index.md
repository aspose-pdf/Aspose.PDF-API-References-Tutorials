---
title: Caselle di controllo raggruppate nel documento PDF
linktitle: Caselle di controllo raggruppate nel documento PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Crea facilmente caselle di controllo raggruppate nei documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 170
url: /it/net/programming-with-forms/grouped-check-boxes/
---
In questo tutorial, ti mostreremo come creare caselle di controllo raggruppate in un documento PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Fase 1: Preparazione

Assicurati di aver importato le librerie necessarie e di aver impostato il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creare un'istanza di un oggetto documento

Crea un'istanza di un oggetto Documento:

```csharp
Document pdfDocument = new Document();
```

## Passaggio 3: aggiungere la pagina al documento PDF

Aggiungere una pagina al documento PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Passaggio 4: creare un'istanza di un oggetto RadioButtonField

Crea un'istanza di un oggetto RadioButtonField con il numero di pagina come argomento:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Passaggio 5: aggiungere le opzioni del pulsante di scelta

Aggiungere le opzioni dei pulsanti di scelta utilizzando l'oggetto RadioButtonOptionField e specificare la loro posizione utilizzando l'oggetto Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Passaggio 6: personalizzare le opzioni del pulsante di scelta

Personalizza le opzioni dei pulsanti di scelta impostandone stile, bordo e aspetto:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Passaggio 7: aggiungere i pulsanti di scelta al modulo

Aggiungere i pulsanti di scelta all'oggetto modulo del documento:

```csharp
pdfDocument.Form.Add(radio);
```

## Passaggio 8: Salvare il documento

Salva il documento PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Grouped Check Boxes utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crea un'istanza dell'oggetto Documento
	Document pdfDocument = new Document();
	// Aggiungere una pagina al file PDF
	Page page = pdfDocument.Pages.Add();
	// Crea un'istanza dell'oggetto RadioButtonField con il numero di pagina come argomento
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Aggiungere la prima opzione del pulsante di scelta e specificare anche la sua origine utilizzando l'oggetto Rettangolo
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Aggiungere il pulsante di scelta all'oggetto modulo dell'oggetto Documento
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Salva il documento PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come creare caselle di controllo raggruppate in un documento PDF usando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente aggiungere opzioni di pulsanti di scelta personalizzati e raggrupparli nei tuoi documenti PDF usando Aspose.PDF.

### Domande frequenti

#### D: Cosa sono le caselle di controllo raggruppate in un documento PDF?

R: Le caselle di controllo raggruppate in un documento PDF si riferiscono a un set di opzioni di pulsanti di scelta che sono raggruppate insieme. I pulsanti di scelta consentono agli utenti di selezionare solo un'opzione da un gruppo di scelte reciprocamente esclusive. Quando viene selezionato un pulsante di scelta, gli altri nello stesso gruppo vengono automaticamente deselezionati. Questo comportamento di raggruppamento è utile quando si desidera presentare agli utenti più opzioni ma limitare la loro selezione a una sola scelta.

#### D: Posso personalizzare l'aspetto delle caselle di controllo raggruppate in Aspose.PDF per .NET?

R: Sì, puoi personalizzare l'aspetto delle caselle di controllo raggruppate in Aspose.PDF per .NET. L'API fornisce varie opzioni per impostare lo stile, il bordo e l'aspetto delle opzioni dei pulsanti di scelta. Puoi definire la posizione di ogni opzione, scegliere tra diversi stili di casella (ad esempio, quadrato, cerchio, croce) e regolare le proprietà del bordo per ottenere la rappresentazione visiva desiderata.

#### D: Come posso aggiungere caselle di controllo raggruppate a una pagina specifica in un documento PDF?

A: Per aggiungere caselle di controllo raggruppate a una pagina specifica in un documento PDF, è necessario creare un'istanza di`RadioButtonField` oggetto con il numero di pagina desiderato come argomento. Quindi, crea`RadioButtonOptionField` oggetti che rappresentano ciascuna opzione del pulsante di scelta e specificano la loro posizione utilizzando`Rectangle` oggetto. Infine, aggiungi queste opzioni al`RadioButtonField` e personalizzarne l'aspetto in base alle necessità prima di aggiungere il`RadioButtonField` al modulo del documento.

#### D: Posso aggiungere più gruppi di caselle di controllo a un singolo documento PDF?

 R: Sì, puoi aggiungere più gruppi di caselle di controllo a un singolo documento PDF. Ogni gruppo dovrebbe avere un nome univoco`RadioButtonField` oggetto e il`RadioButtonOptionField` gli oggetti all'interno di ogni gruppo dovrebbero condividere la stessa pagina e nomi univoci per le loro opzioni. Ciò assicura che i pulsanti di scelta all'interno di ogni gruppo funzionino correttamente e che le selezioni siano reciprocamente esclusive.

#### D: Le caselle di controllo raggruppate sono supportate in tutti i visualizzatori e le applicazioni PDF?

R: Sì, le caselle di controllo raggruppate sono supportate in tutti i visualizzatori e le applicazioni PDF conformi allo standard. La specifica PDF definisce i pulsanti di scelta e il loro comportamento di raggruppamento, rendendoli universalmente riconosciuti nel formato PDF. Tuttavia, è essenziale testare la funzionalità in diversi visualizzatori PDF per garantire un comportamento coerente su diverse piattaforme.