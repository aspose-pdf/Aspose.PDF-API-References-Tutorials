---
title: Recupera campo modulo in ordine di tabulazione
linktitle: Recupera campo modulo in ordine di tabulazione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come recuperare i campi del modulo in ordine di tabulazione utilizzando Aspose.PDF per .NET.
type: docs
weight: 240
url: /it/net/programming-with-forms/retrieve-form-field-in-tab-order/
---

Quando si lavora con documenti PDF in C# utilizzando Aspose.PDF per .NET, è possibile imbattersi in uno scenario in cui è necessario recuperare i campi del modulo in un ordine di tabulazione specifico. Ciò può essere utile quando si desidera eseguire operazioni sui campi del modulo in base alla loro sequenza di tabulazione. In questo tutorial, ti guideremo passo dopo passo su come recuperare i campi del modulo in ordine di tabulazione utilizzando Aspose.PDF per .NET.

## Requisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

- Visual Studio installato nel tuo sistema
- Aspose.PDF per la libreria .NET installata

Ora, tuffiamoci nei passaggi per recuperare i campi del modulo in ordine di tabulazione.

## Passaggio 1: impostazione della directory dei documenti

Per cominciare, devi impostare la directory del documento in cui si trova il tuo documento PDF. Puoi farlo specificando il percorso della directory nel file`dataDir` variabile.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 2: caricamento del documento PDF

 In questo passaggio, caricheremo il documento PDF utilizzando Aspose.PDF per .NET. IL`Document` class offre la possibilità di caricare e manipolare documenti PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Qui,`"Test2.pdf"` è il nome del documento PDF che vuoi caricare. Assicurarsi che il documento sia presente nella directory dei documenti specificata.

## Passaggio 3: recupero dei campi del modulo in ordine di tabulazione

 Per recuperare i campi del modulo in ordine di tabulazione, è necessario accedere al file`FieldsInTabOrder` proprietà del`Page` classe. Questa proprietà restituisce un elenco di campi modulo ordinati in base alla loro sequenza di tabulazione.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Nello snippet di codice sopra, recuperiamo i campi del modulo dalla seconda pagina (`doc.Pages[1]` ) e scorrere ogni campo per concatenare i loro nomi parziali nel file`s` variabile. Puoi modificare questo frammento di codice in base ai tuoi requisiti specifici.

## Passaggio 4: modifica dell'ordine delle schede

 Se desideri modificare l'ordine di tabulazione dei campi del modulo, puoi farlo accedendo al file`TabOrder` proprietà di ciascun campo e assegnando un nuovo valore di ordine di tabulazione. Ecco un esempio:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Nello snippet di codice sopra, assegniamo nuovi valori di ordine di tabulazione a tre campi del modulo (`doc.Form[3]`, `doc.Form[1]` , E`doc.Form[2]`). Regola gli indici dei campi e i valori dell'ordine di tabulazione in base alle tue esigenze specifiche.

## Passaggio 5: salvare il documento modificato

 Dopo aver modificato l'ordine di tabulazione dei campi del modulo, è necessario salvare il documento modificato. Puoi farlo usando il`Save` metodo del`Document` classe.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Qui,`"39522_out.pdf"` è il nome del file di output in cui verrà salvato il documento modificato. Specificare il nome e la posizione desiderati per il file di output.

### Esempio di codice sorgente per Recupera campo modulo in ordine di tabulazione utilizzando Aspose.Words per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Conclusione

In questo tutorial, abbiamo imparato come recuperare i campi del modulo in ordine di tabulazione utilizzando Aspose.PDF per .NET. Abbiamo coperto i passaggi coinvolti nel caricamento di un documento PDF, nel recupero dei campi modulo in ordine di tabulazione, nella modifica dell'ordine di tabulazione e nel salvataggio del documento modificato. Seguendo questi passaggi, puoi lavorare in modo efficiente con i campi modulo e personalizzare la loro sequenza di tabulazione in base alle tue esigenze.