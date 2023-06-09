---
title: Definisci allineamento
linktitle: Definisci allineamento
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come impostare facilmente l'allineamento del testo nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/programming-with-stamps-and-watermarks/define-alignment/
---
In questo tutorial, ti guideremo passo dopo passo su come impostare l'allineamento del testo in un documento PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per creare un timbro di testo centrato nel documento PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: caricamento del documento PDF

Il primo passaggio consiste nel caricare il documento PDF esistente nel progetto. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea un'istanza di un oggetto Document con il file di input
Document doc = new Document(dataDir + "DefineAlignment.pdf");
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: definizione dell'allineamento

Ora che hai caricato il documento PDF, puoi impostare l'allineamento del timbro di testo. Ecco come:

```csharp
// Crea un'istanza di un oggetto FormattedText con la stringa di esempio
FormattedText text = new FormattedText("This");

// Aggiungi una nuova riga di testo a FormattedText
text.AddNewLineText("is an example");
text.AddNewLineText("Center aligned");
text.AddNewLineText("Text buffer");
text.AddNewLineText("Subject");

// Crea un oggetto TextStamp usando FormattedText
TextStamp stamp = new TextStamp(text);

// Specificare l'allineamento orizzontale del buffer di testo come centrato
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Specificare l'allineamento verticale del buffer di testo come centrato
stamp.VerticalAlignment = VerticalAlignment.Center;

// Specificare l'allineamento orizzontale del testo nel TextStamp come centrato
stamp.TextAlignment = HorizontalAlignment.Center;

// Imposta il margine superiore per l'oggetto buffer
stamp. TopMargin = 20;

// Aggiungi l'oggetto timbro alla prima pagina del documento
doc.Pages[1].AddStamp(stamp);
```

Il codice precedente crea un buffer di testo centrato usando la classe FormattedText per specificare il contenuto e imposta l'allineamento orizzontale e verticale del buffer di testo.

## Passaggio 4: salvare il documento di output

Dopo aver impostato l'allineamento del timbro di testo, è possibile salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento aggiornato
doc.Save(dataDir);
```

Il codice precedente salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per Definisci allineamento utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Crea un'istanza dell'oggetto Document con il file di input
Document doc = new Document(dataDir+ "DefineAlignment.pdf");

// Crea un'istanza dell'oggetto FormattedText con una stringa di esempio
FormattedText text = new FormattedText("This");

// Aggiungi una nuova riga di testo a FormattedText
text.AddNewLineText("is sample");
text.AddNewLineText("Center Aligned");
text.AddNewLineText("TextStamp");
text.AddNewLineText("Object");

// Crea un oggetto TextStamp usando FormattedText
TextStamp stamp = new TextStamp(text);

// Specificare l'allineamento orizzontale del timbro di testo come allineato al centro
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Specificare l'allineamento verticale del timbro di testo come allineato al centro
stamp.VerticalAlignment = VerticalAlignment.Center;

// Specificare l'allineamento orizzontale del testo di TextStamp come allineato al centro
stamp.TextAlignment = HorizontalAlignment.Center;

// Imposta il margine superiore per l'oggetto timbro
stamp.TopMargin = 20;

// Aggiungi l'oggetto timbro sulla prima pagina del documento
doc.Pages[1].AddStamp(stamp);
dataDir = dataDir + "StampedPDF_out.pdf";

// Salva il documento aggiornato
doc.Save(dataDir);
Console.WriteLine("\nAlignment defined successfully for text stamp.\nFile saved at " + dataDir);

```

## Conclusione

Congratulazioni! Hai imparato come impostare l'allineamento del testo in un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi applicare questa conoscenza per creare timbri di testo con diversi allineamenti nei tuoi documenti PDF.
