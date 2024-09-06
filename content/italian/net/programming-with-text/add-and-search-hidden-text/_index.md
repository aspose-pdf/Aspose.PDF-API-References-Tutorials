---
title: Aggiungi e cerca testo nascosto nel file PDF
linktitle: Aggiungi e cerca testo nascosto nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo per aggiungere e cercare testo nascosto in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 20
url: /it/net/programming-with-text/add-and-search-hidden-text/
---
In questo tutorial, ti guideremo attraverso come aggiungere e cercare testo nascosto in un file PDF usando Aspose.PDF per .NET. Segui questi passaggi per eseguire questa operazione facilmente.

## 1. Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo installato e configurato.
- Conoscenza di base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata. Puoi scaricarla dal sito ufficiale di Aspose.

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

Assicuratevi di specificare il percorso e il nome file desiderati per il documento PDF.

## 3. Cerca il testo nel documento

Successivamente, cercheremo il testo nascosto nel documento PDF. Utilizza il seguente codice:

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

Verrà effettuato un tentativo di ricerca del testo nascosto nella seconda pagina del documento PDF e verranno visualizzate le informazioni rilevanti.

### Esempio di codice sorgente per aggiungere e cercare testo nascosto utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
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

Congratulazioni! Hai aggiunto e trovato con successo del testo nascosto in un documento PDF usando Aspose.PDF per .NET. Ora puoi applicare questo metodo ai tuoi progetti per manipolare e cercare testo nascosto nei file PDF.

### Domande frequenti

#### D: Che cos'è Aspose.PDF per .NET?

R: Aspose.PDF per .NET è una libreria solida che consente agli sviluppatori di creare, manipolare e trasformare documenti PDF all'interno delle applicazioni .NET.

#### D: È possibile utilizzare il testo nascosto per applicare una filigrana?

R: Assolutamente! Il testo nascosto può essere un mezzo efficace per aggiungere una filigrana ai documenti PDF, aggiungendo un ulteriore livello di sicurezza.

#### D: È possibile rivelare il testo nascosto in un documento PDF?

R: Sì, il processo di ricerca e rivelazione del testo nascosto all'interno di un documento PDF può essere eseguito utilizzando le tecniche descritte in questo tutorial.

#### D: Quali altre funzionalità offre Aspose.PDF per .NET?

R: Oltre alla manipolazione del testo nascosto, Aspose.PDF per .NET offre una vasta gamma di funzionalità, tra cui la generazione di PDF, la conversione, la crittografia e altro ancora.