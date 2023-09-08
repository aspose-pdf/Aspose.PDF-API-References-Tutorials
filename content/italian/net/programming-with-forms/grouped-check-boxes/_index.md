---
title: Caselle di controllo raggruppate nel documento PDF
linktitle: Caselle di controllo raggruppate nel documento PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Crea facilmente caselle di controllo raggruppate nel documento PDF con Aspose.PDF per .NET.
type: docs
weight: 170
url: /it/net/programming-with-forms/grouped-check-boxes/
---
In questo tutorial, ti mostreremo come creare caselle di controllo raggruppate in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creare un'istanza di un oggetto documento

Istanziare un oggetto Document:

```csharp
Document pdfDocument = new Document();
```

## Passaggio 3: aggiungi la pagina al documento PDF

Aggiungi una pagina al documento PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Passaggio 4: creare un'istanza di un oggetto RadioButtonField

Istanziare un oggetto RadioButtonField con il numero di pagina come argomento:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Passaggio 5: aggiungi le opzioni dei pulsanti di opzione

Aggiungi le opzioni dei pulsanti di opzione utilizzando l'oggetto RadioButtonOptionField e specifica la loro posizione utilizzando l'oggetto Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Passaggio 6: personalizza le opzioni dei pulsanti di opzione

Personalizza le opzioni dei pulsanti di opzione impostandone lo stile, il bordo e l'aspetto:

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

## Passaggio 7: aggiungi i pulsanti di opzione al modulo

Aggiungi i pulsanti di opzione all'oggetto modulo del documento:

```csharp
pdfDocument.Form.Add(radio);
```

## Passaggio 8: salva il documento

Salvare il documento PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Codice sorgente di esempio per caselle di controllo raggruppate utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Istanziare l'oggetto Documento
	Document pdfDocument = new Document();
	// Aggiungi una pagina al file PDF
	Page page = pdfDocument.Pages.Add();
	// Crea un oggetto RadioButtonField con il numero di pagina come argomento
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Aggiungi la prima opzione del pulsante di opzione e specifica anche la sua origine utilizzando l'oggetto Rettangolo
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
	// Aggiungi il pulsante di opzione all'oggetto modulo dell'oggetto Documento
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

In questo tutorial, abbiamo imparato come creare caselle di controllo raggruppate in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente aggiungere opzioni personalizzate di pulsanti di opzione e raggrupparle nei tuoi documenti PDF utilizzando Aspose.PDF.

### Domande frequenti

#### D: Cosa sono le caselle di controllo raggruppate in un documento PDF?

R: Le caselle di controllo raggruppate in un documento PDF si riferiscono a una serie di opzioni di pulsanti di opzione raggruppate insieme. I pulsanti di opzione consentono agli utenti di selezionare solo un'opzione da un gruppo di scelte reciprocamente esclusive. Quando viene selezionato un pulsante di opzione, gli altri nello stesso gruppo vengono automaticamente deselezionati. Questo comportamento di raggruppamento è utile quando desideri presentare agli utenti più opzioni ma limitare la loro selezione a una sola scelta.

#### D: Posso personalizzare l'aspetto delle caselle di controllo raggruppate in Aspose.PDF per .NET?

R: Sì, puoi personalizzare l'aspetto delle caselle di controllo raggruppate in Aspose.PDF per .NET. L'API fornisce varie opzioni per impostare lo stile, il bordo e l'aspetto delle opzioni dei pulsanti di opzione. È possibile definire la posizione di ciascuna opzione, scegliere tra diversi stili di riquadro (ad esempio quadrato, cerchio, croce) e regolare le proprietà del bordo per ottenere la rappresentazione visiva desiderata.

#### D: Come posso aggiungere caselle di controllo raggruppate a una pagina specifica in un documento PDF?

R: Per aggiungere caselle di controllo raggruppate a una pagina specifica in un documento PDF, è necessario creare un'istanza di a`RadioButtonField` oggetto con il numero di pagina desiderato come argomento. Quindi, crea`RadioButtonOptionField` oggetti che rappresentano ciascuna opzione del pulsante di opzione e specificano la loro posizione utilizzando il comando`Rectangle` oggetto. Infine, aggiungi queste opzioni al file`RadioButtonField` e personalizzarne l'aspetto secondo necessità prima di aggiungere il file`RadioButtonField` al modulo del documento.

#### D: Posso aggiungere più gruppi di caselle di controllo a un singolo documento PDF?

 R: Sì, puoi aggiungere più gruppi di caselle di controllo a un singolo documento PDF. Ogni gruppo dovrebbe avere un unico`RadioButtonField` oggetto e il`RadioButtonOptionField` gli oggetti all'interno di ciascun gruppo dovrebbero condividere la stessa pagina e nomi univoci per le loro opzioni. Ciò garantisce che i pulsanti di opzione all'interno di ciascun gruppo funzionino correttamente e che le selezioni si escludano a vicenda.

#### D: Le caselle di controllo raggruppate sono supportate in tutti i visualizzatori e applicazioni PDF?

R: Sì, le caselle di controllo raggruppate sono supportate in tutti i visualizzatori e le applicazioni PDF conformi allo standard. La specifica PDF definisce i pulsanti di opzione e il loro comportamento di raggruppamento, rendendoli universalmente riconosciuti nel formato PDF. Tuttavia, è essenziale testare la funzionalità in diversi visualizzatori PDF per garantire un comportamento coerente su varie piattaforme.