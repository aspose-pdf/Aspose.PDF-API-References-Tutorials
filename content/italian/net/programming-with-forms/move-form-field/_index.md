---
title: Sposta campo modulo
linktitle: Sposta campo modulo
second_title: Riferimento API Aspose.PDF per .NET
description: Sposta facilmente i campi modulo nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 200
url: /it/net/programming-with-forms/move-form-field/
---
In questo tutorial, ti mostreremo come spostare un campo modulo in un documento PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Fase 1: Preparazione

Assicurati di aver importato le librerie necessarie e di aver impostato il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento

Carica il documento PDF esistente:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Passaggio 3: Ottieni il campo del modulo

Ottieni il campo del modulo che vuoi spostare:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Passaggio 4: modifica la posizione del campo

Modifica la posizione del campo del modulo definendo una nuova area rettangolare:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Passaggio 5: Salvare il documento modificato

Salvare il documento PDF modificato:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Sposta campo modulo utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Ottieni un campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modifica posizione campo
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Salva il documento modificato
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come spostare un campo modulo in un documento PDF usando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente navigare verso un campo specifico e modificarne la posizione in base alle tue esigenze.


### Domande frequenti

#### D: Posso spostare più campi modulo all'interno di un singolo documento PDF utilizzando Aspose.PDF per .NET?

R: Sì, puoi spostare più campi modulo all'interno di un singolo documento PDF usando Aspose.PDF per .NET. Ripeti semplicemente il processo per ogni campo modulo che vuoi spostare.

#### D: Lo spostamento di un campo di un modulo inciderà sui dati associati o sulla funzionalità?

R: No, spostare un campo modulo non influisce sui dati o sulle funzionalità associati. Il campo modulo mantiene tutte le sue proprietà e i suoi valori dopo essere stato spostato in una nuova posizione.

#### D: Come posso determinare le coordinate esatte per la nuova posizione del campo del modulo?

 A: Puoi specificare la nuova posizione utilizzando`Aspose.Pdf.Rectangle` classe, in cui si definiscono le coordinate X e Y dell'angolo in alto a sinistra e le coordinate X e Y dell'angolo in basso a destra dell'area rettangolare.

#### D: Aspose.PDF per .NET è compatibile sia con gli ambienti Windows che Linux?

R: Sì, Aspose.PDF per .NET è compatibile sia con gli ambienti Windows che Linux, offrendo agli sviluppatori la flessibilità di lavorare sui loro sistemi operativi preferiti.