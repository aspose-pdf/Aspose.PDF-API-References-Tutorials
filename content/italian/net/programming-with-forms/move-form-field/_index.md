---
title: Sposta campo modulo
linktitle: Sposta campo modulo
second_title: Aspose.PDF per riferimento all'API .NET
description: Sposta facilmente i campi del modulo nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 200
url: /it/net/programming-with-forms/move-form-field/
---
In questo tutorial, ti mostreremo come spostare un campo modulo in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento

Carica il documento PDF esistente:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Passaggio 3: ottieni il campo del modulo

Ottieni il campo modulo che desideri spostare:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Passaggio 4: modifica la posizione del campo

Modificare la posizione del campo modulo definendo una nuova area rettangolare:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Passaggio 5: salva il documento modificato

Salvare il documento PDF modificato:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Codice sorgente di esempio per Sposta campo modulo utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Prendi un campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modifica la posizione del campo
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Salva il documento modificato
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come spostare un campo modulo in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente accedere a un campo specifico e modificarne la posizione secondo necessità.


### Domande frequenti

#### D: Posso spostare più campi modulo all'interno di un singolo documento PDF utilizzando Aspose.PDF per .NET?

R: Sì, puoi spostare più campi modulo all'interno di un singolo documento PDF utilizzando Aspose.PDF per .NET. Ripeti semplicemente la procedura per ciascun campo del modulo che desideri riposizionare.

#### D: Lo spostamento di un campo modulo influirà sui dati o sulle funzionalità associati?

R: No, lo spostamento di un campo modulo non influisce sui dati o sulle funzionalità associati. Il campo modulo conserva tutte le sue proprietà e valori dopo essere stato spostato in una nuova posizione.

#### D: Come posso determinare le coordinate esatte per la nuova posizione del campo modulo?

 R: Puoi specificare la nuova posizione utilizzando il file`Aspose.Pdf.Rectangle` classe, in cui definisci le coordinate X e Y dell'angolo in alto a sinistra e le coordinate X e Y dell'angolo in basso a destra dell'area rettangolare.

#### D: Aspose.PDF per .NET è compatibile con ambienti Windows e Linux?

R: Sì, Aspose.PDF per .NET è compatibile sia con gli ambienti Windows che Linux, offrendo agli sviluppatori la flessibilità di lavorare nei loro sistemi operativi preferiti.