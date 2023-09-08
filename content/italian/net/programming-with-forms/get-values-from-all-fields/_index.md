---
title: Ottieni valori da tutti i campi nel documento PDF
linktitle: Ottieni valori da tutti i campi nel documento PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Ottieni facilmente i valori di tutti i campi del modulo nel documento PDF con Aspose.PDF per .NET.
type: docs
weight: 150
url: /it/net/programming-with-forms/get-values-from-all-fields/
---
In questo tutorial, ti mostreremo come ottenere i valori di tutti i campi del modulo in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il documento

Apri il documento PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Passaggio 3: ottieni valori per tutti i campi

Passa in rassegna tutti i campi del modulo nel documento e ottieni i loro nomi e valori:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Codice sorgente di esempio per Ottieni valori da tutti i campi utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Ottieni valori da tutti i campi
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere i valori di tutti i campi del modulo in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente estrarre i valori di tutti i campi del modulo dai tuoi documenti PDF utilizzando Aspose.PDF.

### Domande frequenti

#### D: Posso modificare i valori dei campi del modulo durante il recupero utilizzando Aspose.PDF per .NET?

 R: Sì, puoi modificare i valori dei campi del modulo mentre li recuperi utilizzando Aspose.PDF per .NET. Una volta che hai il`Field` oggetto che rappresenta un campo modulo, puoi aggiornarlo`Value`immobile con il valore desiderato. Dopo aver apportato le modifiche necessarie, è possibile salvare il documento PDF aggiornato per riflettere le modifiche.

#### D: Come posso filtrare e recuperare campi modulo specifici in base al loro tipo (ad esempio, campi di testo, caselle di controllo)?

 R: Per recuperare campi modulo specifici in base al tipo, è possibile utilizzare istruzioni condizionali o query LINQ per filtrare i campi di interesse. Puoi controllare il tipo di ciascun campo del modulo utilizzando i campi`FieldType` proprietà e quindi recuperare i valori di conseguenza.

#### D: Cosa succede se il documento PDF non ha campi modulo?

 R: Se il documento PDF non contiene campi modulo, il file`pdfDocument.Form` la proprietà restituirà una raccolta vuota. In questi casi, il ciclo per recuperare i valori non verrà eseguito e non verrà visualizzato alcun valore.

#### D: Posso estrarre i valori dei campi del modulo in un ordine specifico o ordinarli alfabeticamente?

R: L'ordine in cui vengono recuperati i campi del modulo dipende dalla struttura sottostante del documento PDF. Aspose.PDF per .NET restituisce i campi del modulo nell'ordine in cui sono stati aggiunti al documento. Se desideri visualizzare o elaborare i campi del modulo in un ordine specifico, puoi implementare una logica di ordinamento personalizzata in base alle tue esigenze.

#### D: Come posso gestire documenti PDF crittografati con campi modulo protetti da password?

 R: Aspose.PDF per .NET fornisce funzionalità per lavorare con documenti PDF crittografati e campi modulo protetti da password. Prima di caricare il documento è possibile impostare la password utilizzando il file`pdfDocument.Password` proprietà per accedere al documento PDF protetto e ai relativi campi modulo.