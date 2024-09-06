---
title: Pulsante di scelta
linktitle: Pulsante di scelta
second_title: Riferimento API Aspose.PDF per .NET
description: Aggiungi facilmente pulsanti di scelta ai tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 220
url: /it/net/programming-with-forms/radio-button/
---
In questo tutorial, ti mostreremo come aggiungere un pulsante di scelta in un documento PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Fase 1: Preparazione

Assicurati di aver importato le librerie necessarie e di aver impostato il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creare un'istanza di un oggetto documento

Crea un'istanza di un oggetto Documento per creare un nuovo documento PDF:

```csharp
Document pdfDocument = new Document();
```

## Passaggio 3: aggiungere una pagina

Aggiungere una pagina al documento PDF:

```csharp
pdfDocument.Pages.Add();
```

## Passaggio 4: creare un'istanza di un oggetto RadioButtonField

Crea un'istanza di un oggetto RadioButtonField specificando il numero di pagina come argomento:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Passaggio 5: aggiungere le opzioni del pulsante di scelta

Aggiungere le opzioni del pulsante di scelta all'oggetto RadioButtonField specificando le coordinate di ciascuna opzione con un oggetto Rectangle:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Passaggio 6: aggiungere il pulsante di scelta al modulo

Aggiungere il pulsante di scelta all'oggetto Form del documento:

```csharp
pdfDocument.Form.Add(radio);
```

## Passaggio 7: Salvare il documento PDF

Salvare il documento PDF creato:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per il pulsante di scelta utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crea un'istanza dell'oggetto Documento
	Document pdfDocument = new Document();
	// Aggiungere una pagina al file PDF
	pdfDocument.Pages.Add();
	// Crea un'istanza dell'oggetto RadioButtonField con il numero di pagina come argomento
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Aggiungere la prima opzione del pulsante di scelta e specificare anche la sua origine utilizzando l'oggetto Rettangolo
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Aggiungi seconda opzione pulsante di scelta
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Aggiungere il pulsante di scelta all'oggetto modulo dell'oggetto Documento
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

In questo tutorial, abbiamo imparato come aggiungere un pulsante di scelta in un documento PDF usando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente creare un pulsante di scelta e posizionarlo su una pagina specifica nel tuo documento PDF.


### Domande frequenti

#### D: Posso personalizzare l'aspetto del pulsante di scelta, ad esempio dimensione e colore?

 A: Sì, puoi personalizzare l'aspetto del pulsante di scelta utilizzando`Rectangle` coordinate dell'oggetto per definirne le dimensioni e la posizione. Aspose.PDF per .NET consente di adattare l'aspetto del pulsante di scelta alle proprie esigenze.

#### D: Posso aggiungere più pulsanti di scelta con gruppi diversi nella stessa pagina?

R: Sì, puoi aggiungere più pulsanti di scelta con gruppi diversi nella stessa pagina. Ogni gruppo di pulsanti di scelta può avere un nome univoco e può essere selezionata solo un'opzione alla volta all'interno di ogni gruppo.

#### D: Come posso aggiungere un'etichetta o una descrizione testuale alle opzioni dei pulsanti di scelta?

 A: Per aggiungere un'etichetta o una descrizione di testo alle opzioni del pulsante di scelta, puoi utilizzare`TextStamp`classe di Aspose.PDF per .NET per sovrapporre il testo al documento PDF in corrispondenza di coordinate specifiche.

#### D: Aspose.PDF per .NET è compatibile con tutte le versioni di .NET Framework?

R: Sì, Aspose.PDF per .NET è compatibile con tutte le versioni di .NET Framework, inclusi .NET Core e .NET Standard.

#### D: Posso controllare a livello di programmazione la selezione di un'opzione del pulsante di scelta nel documento PDF?

 A: Sì, puoi controllare a livello di programmazione la selezione di un'opzione del pulsante di scelta utilizzando`IsSelected` proprietà del`RadioButtonOption` classe. Questa proprietà consente di impostare un'opzione specifica come selezionata.