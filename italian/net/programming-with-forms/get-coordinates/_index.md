---
title: Ottieni le coordinate del campo del modulo PDF
linktitle: Ottieni le coordinate del campo del modulo PDF
second_title: Aspose.PDF per riferimento API .NET
description: Ottieni facilmente le coordinate del campo modulo PDF nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-forms/get-coordinates/
---
In questo tutorial, ti mostreremo come ottenere le coordinate del campo del modulo PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e imposta il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento di output

Carica il documento PDF di output:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Passaggio 3: trova i campi aggiunti

Trova i campi del modulo aggiunti (in questo esempio, stiamo usando i campi "Item1", "Item2" e "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Passaggio 4: visualizzare le posizioni degli elementi secondari per ciascun campo

Scorri le opzioni per ogni campo e visualizza le coordinate per ogni sottoelemento:

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

### Esempio di codice sorgente per Ottieni coordinate utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il documento di output
	Document doc1 = new Document( dataDir + "input.pdf");
	// Trova campi aggiunti
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

In questo tutorial, abbiamo imparato come ottenere le coordinate del campo del modulo utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi recuperare facilmente le coordinate dei sottoelementi dei campi del modulo nei tuoi documenti PDF utilizzando Aspose.PDF.

### FAQ

#### D: Posso utilizzare questo metodo per ottenere le coordinate per qualsiasi tipo di campo modulo in Aspose.PDF per .NET?

A: Sì, è possibile utilizzare questo metodo per ottenere le coordinate per vari tipi di campi modulo in Aspose.PDF per .NET. Il codice sorgente C# fornito mostra come ottenere le coordinate per i campi RadioButton, ma puoi adattare lo stesso approccio per altri tipi di campo modulo, ad esempio TextBox, CheckBox, ListBox e altro.

#### D: Come posso modificare o regolare le coordinate del campo del modulo?

R: Le coordinate del campo modulo si basano sul sistema di coordinate del documento PDF, dove l'origine (0,0) si trova nell'angolo in basso a sinistra della pagina. Per modificare o regolare le coordinate del campo del modulo, è possibile aggiornare il file`Rect` proprietà del rispettivo campo modulo o dei suoi elementi secondari, ad esempio RadioButtonOptionField.

#### D: Posso ottenere le coordinate dei campi modulo aggiunti in modo programmatico a un documento PDF?

R: Sì, puoi ottenere le coordinate dei campi modulo che sono stati aggiunti a livello di codice a un documento PDF. Aspose.PDF per .NET ti consente di aggiungere campi modulo in modo dinamico e, una volta aggiunti, puoi recuperare le loro coordinate utilizzando l'approccio dimostrato in questo tutorial.

#### D: Qual è lo scopo del recupero delle coordinate del campo del modulo?

R: Recuperare le coordinate dei campi modulo può essere utile quando è necessario eseguire specifiche operazioni o convalide relative al layout sui campi modulo all'interno di un documento PDF. Ti consente di posizionare e allineare accuratamente i campi del modulo in base alle loro coordinate, assicurando che vengano visualizzati correttamente nel documento e forniscano un'esperienza utente senza interruzioni.

#### D: Le coordinate del campo modulo sono espresse in punti o in un'altra unità?

R: Le coordinate del campo modulo in Aspose.PDF per .NET sono espresse in punti. Un punto equivale a 1/72 di pollice, rendendolo un'unità di misura standard nel formato PDF.