---
title: Recupera il campo del modulo nell'ordine di tabulazione
linktitle: Recupera il campo del modulo nell'ordine di tabulazione
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come recuperare i campi del modulo in ordine di tabulazione utilizzando Aspose.PDF per .NET.
type: docs
weight: 240
url: /it/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Quando lavori con documenti PDF in C# utilizzando Aspose.PDF per .NET, potresti imbatterti in uno scenario in cui è necessario recuperare i campi del modulo in un ordine di tabulazione specifico. Ciò può essere utile quando desideri eseguire operazioni sui campi del modulo in base alla sequenza di tabulazione. In questo tutorial, ti guideremo passo dopo passo su come recuperare i campi del modulo in ordine di tabulazione utilizzando Aspose.PDF per .NET.

## Requisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

- Visual Studio installato nel sistema
- Aspose.PDF per la libreria .NET installata

Ora approfondiamo i passaggi per recuperare i campi del modulo in ordine di tabulazione.

## Passaggio 1: impostazione della directory dei documenti

 Per cominciare, devi impostare la directory dei documenti in cui si trova il tuo documento PDF. Puoi farlo specificando il percorso della directory nel file`dataDir` variabile.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 2: caricamento del documento PDF

 In questo passaggio, caricheremo il documento PDF utilizzando Aspose.PDF per .NET. IL`Document` La classe offre la possibilità di caricare e manipolare documenti PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Qui,`"Test2.pdf"`è il nome del documento PDF che desideri caricare. Assicurati che il documento sia presente nella directory dei documenti specificata.

## Passaggio 3: recupero dei campi del modulo nell'ordine delle schede

 Per recuperare i campi del modulo in ordine di tabulazione, dobbiamo accedere a`FieldsInTabOrder` proprietà del`Page` classe. Questa proprietà restituisce un elenco di campi modulo ordinati in base alla sequenza di tabulazione.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Nello snippet di codice sopra, recuperiamo i campi del modulo dalla seconda pagina (`doc.Pages[1]` ) e scorrere ciascun campo per concatenare i relativi nomi parziali nel file`s` variabile. Puoi modificare questo snippet di codice in base ai tuoi requisiti specifici.

## Passaggio 4: modifica dell'ordine delle schede

 Se desideri modificare l'ordine di tabulazione dei campi del modulo, puoi farlo accedendo al file`TabOrder` proprietà di ciascun campo e assegnando un nuovo valore dell'ordine di tabulazione. Ecco un esempio:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Nello snippet di codice sopra, assegniamo nuovi valori dell'ordine di tabulazione a tre campi del modulo (`doc.Form[3]`, `doc.Form[1]` , E`doc.Form[2]`). Modifica gli indici dei campi e i valori dell'ordine di tabulazione in base ai tuoi requisiti specifici.

## Passaggio 5: salvataggio del documento modificato

 Dopo aver modificato l'ordine di tabulazione dei campi del modulo, è necessario salvare il documento modificato. Puoi farlo usando il file`Save` metodo del`Document` classe.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Qui,`"39522_out.pdf"` è il nome del file di output in cui verrà salvato il documento modificato. Specificare il nome e il percorso desiderati per il file di output.

### Codice sorgente di esempio per Recupera campo modulo nell'ordine di tabulazione utilizzando Aspose.PDF per .NET 
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

In questo tutorial, abbiamo imparato come recuperare i campi del modulo in ordine di tabulazione utilizzando Aspose.PDF per .NET. Abbiamo coperto i passaggi necessari per caricare un documento PDF, recuperare i campi del modulo in ordine di tabulazione, modificare l'ordine di tabulazione e salvare il documento modificato. Seguendo questi passaggi, puoi lavorare in modo efficiente con i campi del modulo e personalizzare la sequenza delle schede in base alle tue esigenze.


### Domande frequenti

#### D: Come posso utilizzare i campi del modulo recuperati nel mio codice C# per un'ulteriore elaborazione?

 R: Puoi utilizzare i campi del modulo recuperati nel codice C# accedendo alle loro proprietà come`Value`, `Name`, `Rect`ecc. Queste proprietà consentono di leggere e modificare i dati del campo modulo secondo necessità.

#### D: Posso recuperare i campi modulo da tutte le pagine del documento PDF in ordine di tabulazione?

 R: Sì, puoi recuperare i campi modulo da tutte le pagine del documento PDF scorrendo ciascuna pagina e accedendo al file`FieldsInTabOrder` proprietà come mostrato nel tutorial. Questo ti darà i campi del modulo ordinati in base alla sequenza di tabulazione su tutte le pagine.

#### D: È possibile recuperare solo tipi specifici di campi modulo, come campi di testo o caselle di controllo, in ordine di tabulazione?

R: Sì, puoi filtrare i campi del modulo in base al loro tipo, come campi di testo o caselle di controllo, dopo averli recuperati in ordine di tabulazione. È possibile utilizzare istruzioni condizionali per verificare il tipo di ciascun campo del modulo ed elaborarli di conseguenza.

#### D: Posso recuperare i campi del modulo in base ai nomi anziché all'ordine di tabulazione?

 R: Sì, puoi recuperare i campi del modulo in base ai loro nomi utilizzando il file`doc.Form` collection e specificando il nome del campo come indice. Per esempio,`doc.Form["fieldName"]`recupererà il campo del modulo con il nome specificato.

#### D: Aspose.PDF per .NET supporta il lavoro con documenti PDF crittografati?

R: Sì, Aspose.PDF per .NET fornisce supporto per lavorare con documenti PDF crittografati. È possibile caricare e manipolare file PDF crittografati utilizzando parametri di password appropriati.