---
title: Ottieni le coordinate del campo del modulo PDF
linktitle: Ottieni le coordinate del campo del modulo PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Ottieni facilmente le coordinate dei campi dei moduli PDF nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-forms/get-coordinates/
---
In questo tutorial, ti mostreremo come ottenere le coordinate dei campi del modulo PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Fase 1: Preparazione

Assicurati di aver importato le librerie necessarie e di aver impostato il percorso alla directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento di output

Carica il documento PDF di output:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Passaggio 3: trova i campi aggiunti

Trova i campi del modulo aggiunti (in questo esempio, stiamo utilizzando i campi "Item1", "Item2" e "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Passaggio 4: visualizzare le posizioni dei sottoelementi per ciascun campo

Scorrere le opzioni per ogni campo e visualizzare le coordinate per ogni sottoelemento:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Esempio di codice sorgente per ottenere coordinate utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il documento di output
	Document doc1 = new Document( dataDir + "input.pdf");
	// Trova i campi aggiunti
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// E mostra le posizioni degli elementi secondari per ciascuno di essi.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere le coordinate dei campi del modulo usando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente recuperare le coordinate dei sottoelementi dei campi del modulo nei tuoi documenti PDF usando Aspose.PDF.

### Domande frequenti

#### D: Posso usare questo metodo per ottenere le coordinate per qualsiasi tipo di campo modulo in Aspose.PDF per .NET?

R: Sì, puoi usare questo metodo per ottenere le coordinate per vari tipi di campi modulo in Aspose.PDF per .NET. Il codice sorgente C# fornito dimostra come ottenere le coordinate per i campi RadioButton, ma puoi adattare lo stesso approccio per altri tipi di campi modulo, come TextBox, CheckBox, ListBox e altri.

#### D: Come posso modificare o aggiustare le coordinate del campo del modulo?

A: Le coordinate del campo modulo si basano sul sistema di coordinate del documento PDF, dove l'origine (0,0) si trova nell'angolo in basso a sinistra della pagina. Per modificare o regolare le coordinate del campo modulo, puoi aggiornare`Rect` proprietà del rispettivo campo del modulo o dei suoi sottoelementi, ad esempio RadioButtonOptionField.

#### D: Posso aggiungere le coordinate dei campi modulo a un documento PDF tramite programmazione?

R: Sì, puoi ottenere le coordinate dei campi modulo aggiunti a livello di programmazione a un documento PDF. Aspose.PDF per .NET ti consente di aggiungere campi modulo in modo dinamico e, una volta aggiunti, puoi recuperare le loro coordinate utilizzando l'approccio dimostrato in questo tutorial.

#### D: Qual è lo scopo del recupero delle coordinate dei campi del modulo?

R: Il recupero delle coordinate dei campi modulo può essere utile quando è necessario eseguire operazioni specifiche relative al layout o convalide sui campi modulo all'interno di un documento PDF. Consente di posizionare e allineare con precisione i campi modulo in base alle loro coordinate, assicurando che appaiano correttamente nel documento e forniscano un'esperienza utente fluida.

#### D: Le coordinate del campo modulo sono espresse in punti o in un'altra unità?

R: Le coordinate del campo modulo in Aspose.PDF per .NET sono espresse in punti. Un punto equivale a 1/72 di pollice, rendendolo un'unità di misura standard nel formato PDF.