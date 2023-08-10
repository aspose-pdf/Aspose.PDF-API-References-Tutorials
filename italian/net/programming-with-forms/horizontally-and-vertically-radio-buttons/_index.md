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
formEditor. RadioHoriz = true; //Disposizione orizzontale dei pulsanti di opzione
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

### FAQ

#### D: Cosa sono i pulsanti di opzione disposti orizzontalmente e verticalmente in un documento PDF?

R: I pulsanti di opzione disposti orizzontalmente e verticalmente in un documento PDF si riferiscono all'orientamento del layout delle opzioni dei pulsanti di opzione. Il layout orizzontale affianca le opzioni del pulsante di opzione, consentendo agli utenti di effettuare una selezione da sinistra a destra. Il layout verticale, d'altra parte, impila le opzioni del pulsante di opzione una sopra l'altra, consentendo agli utenti di effettuare una selezione dall'alto verso il basso.

#### D: Come si personalizza l'aspetto delle opzioni dei pulsanti di opzione in Aspose.PDF per .NET?

A: È possibile personalizzare l'aspetto delle opzioni del pulsante di opzione in Aspose.PDF per .NET regolando diverse proprietà. L'API fornisce opzioni per impostare la distanza tra due opzioni del pulsante di opzione (`RadioGap`), l'orientamento del layout (`RadioHoriz`), la dimensione degli elementi del pulsante di opzione (`RadioButtonItemSize`), la larghezza del bordo e il colore dei pulsanti di opzione e altro ancora.

#### D: Posso aggiungere pulsanti di opzione sia orizzontali che verticali allo stesso documento PDF?

R: Sì, puoi aggiungere pulsanti di opzione sia orizzontali che verticali allo stesso documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente di esempio fornito nell'esercitazione mostra come aggiungere prima i pulsanti di opzione disposti orizzontalmente e quindi aggiungere un altro set di pulsanti di opzione disposti verticalmente allo stesso documento PDF.

#### D: Posso impostare opzioni di pulsanti di opzione diverse per ciascun gruppo di pulsanti di opzione?

 R: Sì, puoi impostare diverse opzioni di pulsanti di opzione per ciascun gruppo di pulsanti di opzione. Ogni gruppo dovrebbe avere un unico`RadioButtonField` oggetto, e il`RadioButtonOptionField` gli oggetti all'interno di ogni gruppo dovrebbero condividere la stessa pagina e nomi univoci per le loro opzioni. Ciò garantisce che i pulsanti di opzione all'interno di ciascun gruppo funzionino correttamente e che le selezioni si escludano a vicenda.

#### D: Le impostazioni di layout e aspetto dei pulsanti di opzione sono supportate in tutti i visualizzatori e le applicazioni PDF?

R: Sì, le impostazioni di layout e aspetto dei pulsanti di opzione sono supportate in tutti i visualizzatori e le applicazioni PDF conformi agli standard. La specifica PDF definisce i pulsanti di opzione ei loro vari attributi, rendendoli universalmente riconosciuti nel formato PDF. Tuttavia, è essenziale testare l'aspetto e il comportamento dei pulsanti di opzione in diversi visualizzatori di PDF per garantire un rendering coerente su varie piattaforme.