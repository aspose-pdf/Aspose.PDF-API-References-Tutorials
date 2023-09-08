---
title: Pulsante di opzione
linktitle: Pulsante di opzione
second_title: Aspose.PDF per riferimento all'API .NET
description: Aggiungi facilmente pulsanti di opzione ai tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 220
url: /it/net/programming-with-forms/radio-button/
---
In questo tutorial, ti mostreremo come aggiungere un pulsante di opzione in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creare un'istanza di un oggetto documento

Istanziare un oggetto Document per creare un nuovo documento PDF:

```csharp
Document pdfDocument = new Document();
```

## Passaggio 3: aggiungi una pagina

Aggiungi una pagina al documento PDF:

```csharp
pdfDocument.Pages.Add();
```

## Passaggio 4: creare un'istanza di un oggetto RadioButtonField

Istanziare un oggetto RadioButtonField specificando il numero di pagina come argomento:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Passaggio 5: aggiungi le opzioni dei pulsanti di opzione

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

Salvare il documento PDF creato:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Codice sorgente di esempio per Radio Button utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Istanziare l'oggetto Documento
	Document pdfDocument = new Document();
	// Aggiungi una pagina al file PDF
	pdfDocument.Pages.Add();
	// Crea un oggetto RadioButtonField con il numero di pagina come argomento
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Aggiungi la prima opzione del pulsante di opzione e specifica anche la sua origine utilizzando l'oggetto Rettangolo
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Aggiungi l'opzione del secondo pulsante di opzione
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Aggiungi il pulsante di opzione all'oggetto modulo dell'oggetto Documento
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Salvare il file PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come aggiungere un pulsante di opzione in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente creare un pulsante di opzione e posizionarlo su una pagina specifica del tuo documento PDF.


### Domande frequenti

#### D: Posso personalizzare l'aspetto del pulsante di opzione, ad esempio dimensioni e colore?

 R: Sì, puoi personalizzare l'aspetto del pulsante di opzione utilizzando`Rectangle` le coordinate dell'oggetto per definirne le dimensioni e la posizione. Aspose.PDF per .NET ti consente di regolare l'aspetto del pulsante di opzione in base alle tue esigenze.

#### D: Posso aggiungere più pulsanti di opzione con gruppi diversi sulla stessa pagina?

R: Sì, puoi aggiungere più pulsanti di opzione con gruppi diversi sulla stessa pagina. Ciascun gruppo di pulsanti di opzione può avere un nome univoco ed è possibile selezionare solo un'opzione alla volta all'interno di ciascun gruppo.

#### D: Come posso aggiungere un'etichetta o una descrizione testuale alle opzioni del pulsante di opzione?

 R: Per aggiungere un'etichetta o una descrizione testuale alle opzioni del pulsante di opzione, puoi utilizzare il file`TextStamp`classe da Aspose.PDF per .NET per sovrapporre il testo sul documento PDF a coordinate specifiche.

#### D: Aspose.PDF per .NET è compatibile con tutte le versioni di .NET Framework?

R: Sì, Aspose.PDF per .NET è compatibile con tutte le versioni di .NET Framework, inclusi .NET Core e .NET Standard.

#### D: Posso controllare a livello di codice la selezione di un'opzione del pulsante di opzione nel documento PDF?

 R: Sì, puoi controllare a livello di codice la selezione di un'opzione del pulsante di opzione utilizzando`IsSelected` proprietà del`RadioButtonOption` classe. Questa proprietà consente di impostare un'opzione specifica come selezionata.