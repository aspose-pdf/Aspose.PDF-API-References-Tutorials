---
title: Recupera il campo del modulo nell'ordine di tabulazione
linktitle: Recupera il campo del modulo nell'ordine di tabulazione
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come recuperare i campi del modulo in ordine di tabulazione utilizzando Aspose.PDF per .NET.
type: docs
weight: 240
url: /it/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Quando si lavora con documenti PDF in C# usando Aspose.PDF per .NET, ci si può imbattere in uno scenario in cui è necessario recuperare i campi del modulo in un ordine di tabulazione specifico. Ciò può essere utile quando si desidera eseguire operazioni sui campi del modulo in base alla loro sequenza di tabulazione. In questo tutorial, ti guideremo passo dopo passo su come recuperare i campi del modulo in ordine di tabulazione usando Aspose.PDF per .NET.

## Requisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Visual Studio installato sul tuo sistema
- Aspose.PDF per la libreria .NET installata

Ora analizziamo i passaggi per recuperare i campi del modulo in ordine di tabulazione.

## Passaggio 1: impostazione della directory dei documenti

 Per iniziare, devi impostare la directory del documento in cui si trova il tuo documento PDF. Puoi farlo specificando il percorso della directory nel`dataDir` variabile.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

## Passaggio 2: caricamento del documento PDF

 In questo passaggio, caricheremo il documento PDF utilizzando Aspose.PDF per .NET. Il`Document` La classe offre la possibilità di caricare e manipolare documenti PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Qui,`"Test2.pdf"`è il nome del documento PDF che vuoi caricare. Assicurati che il documento sia presente nella directory specificata.

## Passaggio 3: recupero dei campi del modulo in ordine di tabulazione

 Per recuperare i campi del modulo in ordine di tabulazione, dobbiamo accedere a`FieldsInTabOrder` proprietà del`Page` classe. Questa proprietà restituisce un elenco di campi del modulo ordinati in base alla loro sequenza di tabulazione.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Nel frammento di codice soprastante, recuperiamo i campi del modulo dalla seconda pagina (`doc.Pages[1]` ) e scorrere ogni campo per concatenare i loro nomi parziali nel`s` variabile. Puoi modificare questo frammento di codice in base alle tue esigenze specifiche.

## Passaggio 4: modifica dell'ordine delle schede

 Se si desidera modificare l'ordine di tabulazione dei campi del modulo, è possibile farlo accedendo al`TabOrder` proprietà di ogni campo e assegnando un nuovo valore di ordine di tabulazione. Ecco un esempio:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Nel frammento di codice soprastante, assegniamo nuovi valori di ordine di tabulazione a tre campi del modulo (`doc.Form[3]`, `doc.Form[1]` , E`doc.Form[2]`). Adatta gli indici dei campi e i valori dell'ordine di tabulazione in base alle tue esigenze specifiche.

## Passaggio 5: salvataggio del documento modificato

 Dopo aver modificato l'ordine di tabulazione dei campi del modulo, è necessario salvare il documento modificato. È possibile farlo utilizzando`Save` metodo del`Document` classe.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Qui,`"39522_out.pdf"` è il nome del file di output in cui verrà salvato il documento modificato. Specificare il nome e la posizione desiderati per il file di output.

### Esempio di codice sorgente per recuperare il campo del modulo in ordine di tabulazione utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
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

In questo tutorial, abbiamo imparato come recuperare i campi del modulo in ordine di tabulazione usando Aspose.PDF per .NET. Abbiamo trattato i passaggi necessari per caricare un documento PDF, recuperare i campi del modulo in ordine di tabulazione, modificare l'ordine di tabulazione e salvare il documento modificato. Seguendo questi passaggi, puoi lavorare in modo efficiente con i campi del modulo e personalizzare la loro sequenza di tabulazione in base alle tue esigenze.


### Domande frequenti

#### D: Come posso utilizzare i campi del modulo recuperati nel mio codice C# per ulteriori elaborazioni?

 A: Puoi utilizzare i campi del modulo recuperati nel tuo codice C# accedendo alle loro proprietà come`Value`, `Name`, `Rect`ecc. Queste proprietà consentono di leggere e modificare i dati dei campi del modulo in base alle proprie esigenze.

#### D: Posso recuperare i campi modulo da tutte le pagine del documento PDF in ordine di tabulazione?

 A: Sì, puoi recuperare i campi del modulo da tutte le pagine del documento PDF scorrendo ogni pagina e accedendo al`FieldsInTabOrder` proprietà come mostrato nel tutorial. Questo ti darà campi del modulo ordinati in base alla loro sequenza di tabulazione in tutte le pagine.

#### D: È possibile recuperare solo tipi specifici di campi modulo, come campi di testo o caselle di controllo, nell'ordine di tabulazione?

R: Sì, puoi filtrare i campi del modulo in base al loro tipo, come campi di testo o caselle di controllo, dopo averli recuperati in ordine di tabulazione. Puoi usare istruzioni condizionali per controllare il tipo di ogni campo del modulo ed elaborarli di conseguenza.

#### D: Posso recuperare i campi del modulo in base ai loro nomi anziché in base all'ordine di tabulazione?

 A: Sì, puoi recuperare i campi del modulo in base ai loro nomi utilizzando`doc.Form` raccolta e specificando il nome del campo come indice. Ad esempio,`doc.Form["fieldName"]`recupererà il campo del modulo con il nome specificato.

#### D: Aspose.PDF per .NET supporta l'utilizzo di documenti PDF crittografati?

R: Sì, Aspose.PDF per .NET fornisce supporto per lavorare con documenti PDF crittografati. Puoi caricare e manipolare file PDF crittografati utilizzando parametri di password appropriati.