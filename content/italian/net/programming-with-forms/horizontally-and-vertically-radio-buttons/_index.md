---
title: Pulsanti di scelta orizzontali e verticali
linktitle: Pulsanti di scelta orizzontali e verticali
second_title: Riferimento API Aspose.PDF per .NET
description: Crea facilmente pulsanti di scelta orizzontali e verticali nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 180
url: /it/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
In questo tutorial, ti mostreremo come creare pulsanti di scelta disposti orizzontalmente e verticalmente in un documento PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Fase 1: Preparazione

Assicurati di aver importato le librerie necessarie e di aver impostato il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento

Carica il documento PDF esistente:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Passaggio 3: personalizzare le opzioni del pulsante di scelta

Personalizza le opzioni del pulsante di scelta impostando le seguenti proprietà:

```csharp
formEditor. RadioGap = 4; // Distanza tra due opzioni del pulsante di scelta
formEditor. RadioHoriz = true; //Disposizione orizzontale dei pulsanti di scelta
formEditor.RadioButtonItemSize = 20; // Dimensioni dei pulsanti di scelta
formEditor.Facade.BorderWidth = 1; // Larghezza del bordo del pulsante di scelta
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Colore del bordo del pulsante di scelta
```

## Passaggio 4: aggiungere pulsanti di scelta orizzontali

Aggiungere pulsanti di scelta disposti orizzontalmente specificando le opzioni e la posizione del campo:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Passaggio 5: aggiungere pulsanti di scelta verticali

Aggiungere pulsanti di scelta disposti verticalmente specificando le opzioni e la posizione del campo:

```csharp
formEditor. RadioHoriz = false; // Disposizione verticale dei pulsanti di scelta
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Passaggio 6: Salvare il documento

Salvare il documento PDF modificato:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Esempio di codice sorgente per pulsanti di scelta orizzontali e verticali utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il documento salvato in precedenza
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap è la distanza tra due opzioni del pulsante di scelta.
	formEditor.RadioGap = 4;
	// Aggiungi pulsante di scelta orizzontale
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize se è la dimensione dell'elemento del pulsante di scelta.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Aggiungere un altro pulsante di scelta situato verticalmente
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

In questo tutorial, abbiamo imparato come creare pulsanti di scelta disposti orizzontalmente e verticalmente in un documento PDF usando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente personalizzare il layout dei pulsanti di scelta e aggiungerli ai tuoi documenti PDF usando Aspose.PDF.

### Domande frequenti

#### D: Cosa sono i pulsanti di scelta disposti orizzontalmente e verticalmente in un documento PDF?

R: I pulsanti di scelta disposti orizzontalmente e verticalmente in un documento PDF si riferiscono all'orientamento del layout delle opzioni dei pulsanti di scelta. Il layout orizzontale posiziona le opzioni dei pulsanti di scelta una accanto all'altra, consentendo agli utenti di effettuare una selezione da sinistra a destra. Il layout verticale, d'altro canto, impila le opzioni dei pulsanti di scelta una sopra l'altra, consentendo agli utenti di effettuare una selezione dall'alto verso il basso.

#### D: Come posso personalizzare l'aspetto delle opzioni dei pulsanti di scelta in Aspose.PDF per .NET?

A: È possibile personalizzare l'aspetto delle opzioni dei pulsanti di scelta in Aspose.PDF per .NET regolando diverse proprietà. L'API fornisce opzioni per impostare la distanza tra due opzioni dei pulsanti di scelta (`RadioGap`), l'orientamento del layout (`RadioHoriz`), la dimensione degli elementi del pulsante di scelta (`RadioButtonItemSize`), la larghezza del bordo e il colore dei pulsanti di scelta e altro ancora.

#### D: Posso aggiungere pulsanti di scelta orizzontali e verticali allo stesso documento PDF?

R: Sì, puoi aggiungere pulsanti di scelta orizzontali e verticali allo stesso documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente di esempio fornito nel tutorial mostra come aggiungere prima pulsanti di scelta disposti orizzontalmente e poi aggiungere un altro set di pulsanti di scelta disposti verticalmente allo stesso documento PDF.

#### D: Posso impostare opzioni diverse per ogni gruppo di pulsanti di scelta?

 A: Sì, puoi impostare diverse opzioni di pulsanti di scelta per ogni gruppo di pulsanti di scelta. Ogni gruppo dovrebbe avere un'opzione univoca`RadioButtonField` oggetto e il`RadioButtonOptionField` gli oggetti all'interno di ogni gruppo dovrebbero condividere la stessa pagina e nomi univoci per le loro opzioni. Ciò assicura che i pulsanti di scelta all'interno di ogni gruppo funzionino correttamente e che le selezioni siano reciprocamente esclusive.

#### D: Le impostazioni di layout e aspetto dei pulsanti di scelta sono supportate in tutti i visualizzatori e le applicazioni PDF?

R: Sì, le impostazioni di layout e aspetto dei pulsanti di scelta sono supportate in tutti i visualizzatori e le applicazioni PDF conformi allo standard. La specifica PDF definisce i pulsanti di scelta e i loro vari attributi, rendendoli universalmente riconosciuti nel formato PDF. Tuttavia, è essenziale testare l'aspetto e il comportamento dei pulsanti di scelta in diversi visualizzatori PDF per garantire un rendering coerente su diverse piattaforme.