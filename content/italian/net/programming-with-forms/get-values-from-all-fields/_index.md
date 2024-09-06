---
title: Ottieni valori da tutti i campi nel documento PDF
linktitle: Ottieni valori da tutti i campi nel documento PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Ottieni facilmente i valori di tutti i campi del modulo in un documento PDF con Aspose.PDF per .NET.
type: docs
weight: 150
url: /it/net/programming-with-forms/get-values-from-all-fields/
---
In questo tutorial, ti mostreremo come ottenere i valori di tutti i campi del modulo in un documento PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Fase 1: Preparazione

Assicurati di aver importato le librerie necessarie e di aver impostato il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: aprire il documento

Aprire il documento PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Passaggio 3: ottenere i valori per tutti i campi

Esegui un ciclo attraverso tutti i campi del modulo nel documento e ottieni i loro nomi e valori:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Esempio di codice sorgente per ottenere valori da tutti i campi utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
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

In questo tutorial, abbiamo imparato come ottenere i valori di tutti i campi modulo in un documento PDF usando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente estrarre i valori di tutti i campi modulo dai tuoi documenti PDF usando Aspose.PDF.

### Domande frequenti

#### D: Posso modificare i valori dei campi del modulo mentre li recupero utilizzando Aspose.PDF per .NET?

 A: Sì, puoi modificare i valori dei campi del modulo mentre li recuperi usando Aspose.PDF per .NET. Una volta che hai il`Field` oggetto che rappresenta un campo del modulo, è possibile aggiornarlo`Value`proprietà con il valore desiderato. Dopo aver apportato le modifiche necessarie, puoi salvare il documento PDF aggiornato per riflettere le modifiche.

#### D: Come posso filtrare e recuperare campi specifici di un modulo in base alla loro tipologia (ad esempio campi di testo, caselle di controllo)?

 A: Per recuperare campi di form specifici in base ai loro tipi, puoi usare istruzioni condizionali o query LINQ per filtrare i campi di interesse. Puoi controllare il tipo di ogni campo di form usando il campo`FieldType` proprietà e quindi recuperare i valori di conseguenza.

#### D: Cosa succede se il documento PDF non contiene campi modulo?

 A: Se il documento PDF non contiene alcun campo modulo, il`pdfDocument.Form` property restituirà una raccolta vuota. In tali casi, il ciclo per recuperare i valori non verrà eseguito e non verrà visualizzato alcun valore.

#### D: Posso estrarre i valori dei campi del modulo in un ordine specifico o ordinarli alfabeticamente?

R: L'ordine in cui vengono recuperati i campi del modulo dipende dalla struttura sottostante del documento PDF. Aspose.PDF per .NET restituisce i campi del modulo nell'ordine in cui sono stati aggiunti al documento. Se si desidera visualizzare o elaborare i campi del modulo in un ordine specifico, è possibile implementare una logica di ordinamento personalizzata in base alle proprie esigenze.

#### D: Come posso gestire i documenti PDF crittografati con campi modulo protetti da password?

 A: Aspose.PDF per .NET fornisce funzionalità per lavorare con documenti PDF crittografati e campi modulo protetti da password. Prima di caricare il documento, puoi impostare la password utilizzando`pdfDocument.Password` proprietà per accedere al documento PDF protetto e ai suoi campi modulo.