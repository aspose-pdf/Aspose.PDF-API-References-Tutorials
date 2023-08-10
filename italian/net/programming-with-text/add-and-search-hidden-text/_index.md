---
title: Aggiungi e cerca testo nascosto
linktitle: Aggiungi e cerca testo nascosto
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata per aggiungere e cercare testo nascosto in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 20
url: /it/net/programming-with-text/add-and-search-hidden-text/
---

In questo tutorial, ti illustreremo come aggiungere e cercare testo nascosto in un documento PDF utilizzando Aspose.PDF per .NET. Segui questi passaggi per eseguire facilmente questa operazione.

## 1. Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza di base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarlo dal sito ufficiale di Aspose.

## 2. Creazione del documento PDF con testo nascosto

Per iniziare, utilizza il seguente codice per creare un nuovo documento PDF contenente testo nascosto:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Crea un documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Imposta la proprietà del testo - invisibile
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Assicurati di fornire il percorso e il nome file desiderati per il documento PDF.

## 3. Cerca il testo nel documento

Successivamente, cercheremo il testo nascosto nel documento PDF. Usa il seguente codice:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Fai qualcosa con i frammenti
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Questo cercherà il testo nascosto nella seconda pagina del documento PDF e visualizzerà le informazioni pertinenti.

### Esempio di codice sorgente per Aggiungi e cerca testo nascosto utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Crea documento con testo nascosto
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Imposta la proprietà del testo - invisibile
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Cerca testo nel documento
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Fai qualcosa con i frammenti
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Conclusione

Congratulazioni! Hai aggiunto e trovato correttamente il testo nascosto in un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per manipolare e cercare il testo nascosto nei file PDF.