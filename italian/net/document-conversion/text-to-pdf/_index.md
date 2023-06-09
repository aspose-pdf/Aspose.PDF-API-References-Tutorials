---
title: Testo in PDF
linktitle: Testo in PDF
second_title: Aspose.PDF per riferimento API .NET
description: Conversione semplice ed efficiente di file di testo in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 300
url: /it/net/document-conversion/text-to-pdf/
---

Questo tutorial ti guiderà attraverso i passaggi per convertire un file di testo in un file PDF utilizzando Aspose.PDF per .NET. Aspose.PDF offre una soluzione semplice ed efficace per convertire testo semplice in PDF preservando la formattazione e la presentazione del testo. Seguire i passaggi seguenti per eseguire questa conversione.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: lettura del file di testo
 Il primo passo è leggere il contenuto del file di testo usando l'estensione`StreamReader` classe. Usa il seguente codice:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Leggi il file di testo
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file di testo.

## Passaggio 2: creazione del documento PDF
 Il secondo passaggio consiste nel creare un file`Document` oggetto che rappresenterà il documento PDF finale. Usa il seguente codice:

```csharp
// Creare un oggetto documento
Document doc = new Document();
```

## Passaggio 3: aggiungi testo al documento
Il terzo passaggio consiste nell'aggiungere il testo letto alla pagina del documento PDF. Usa il seguente codice:

```csharp
// Aggiungi una nuova pagina al documento
Page page = doc.Pages.Add();

//Crea un oggetto TextFragment e passa il testo letto come argomento
TextFragment text = new TextFragment(tr.ReadToEnd());

// Aggiungi il paragrafo di testo alla pagina
page.Paragraphs.Add(text);
```

## Passaggio 4: salvare il file PDF
Infine, salva il file PDF risultante specificando il percorso e il nome file desiderati. Usa il seguente codice:

```csharp
// Salva il file PDF risultante
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

Assicurati di specificare il percorso e il nome file desiderati per il file PDF risultante.

### Esempio di codice sorgente per Text to PDF utilizzando Aspose.PDF per .NET

```csharp
try
{
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Leggi il file di testo sorgente
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// Crea un'istanza di un oggetto Document chiamando il suo costruttore vuoto
	Document doc = new Document();

	// Aggiungi una nuova pagina nella raccolta Pages di Document
	Page page = doc.Pages.Add();

	// Crea un'istanza di TextFragmet e passa il testo dall'oggetto lettore al suo costruttore come argomento
	TextFragment text = new TextFragment(tr.ReadToEnd());
	// Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// Aggiungi un nuovo paragrafo di testo nella raccolta di paragrafi e passa l'oggetto TextFragment
	page.Paragraphs.Add(text);

	// Salva il file PDF risultante
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione
In questo tutorial, abbiamo imparato come convertire un file di testo in un file PDF utilizzando Aspose.PDF per .NET. Seguendo i passaggi sopra indicati, puoi eseguire facilmente questa conversione. Usa questo metodo per convertire i tuoi file di testo in PDF e goditi la flessibilità e la qualità di Aspose.PDF.