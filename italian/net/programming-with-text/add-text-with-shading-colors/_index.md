---
title: Aggiungi testo con colori di ombreggiatura
linktitle: Aggiungi testo con colori di ombreggiatura
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere testo con colori sfumati a un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-text/add-text-with-shading-colors/
---

Questo tutorial ti guiderà attraverso il processo di aggiunta di testo con colori di ombreggiatura utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di disporre di quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato nel tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere testo con colori di ombreggiatura, aggiungi la seguente direttiva using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Passaggio 3: impostare la directory dei documenti
 Nel codice, individuare la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i documenti.

## Passaggio 4: caricare il documento PDF
 Carica il documento PDF esistente utilizzando il file`Document` costruttore e fornire il percorso del file del documento.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Il codice va qui...
}
```

## Passaggio 5: trova il testo da modificare
 Utilizzo`TextFragmentAbsorber` per trovare il testo desiderato all'interno del documento. Nel codice fornito, cerca il testo "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Passaggio 6: imposta il colore dell'ombreggiatura per il testo
 Crea un nuovo`Color` oggetto con uno spazio colore modello e specificare i colori di sfumatura sfumatura. Assegna questo colore al`ForegroundColor` proprietà del`TextState` del`TextFragment` oggetto.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Passaggio 7: applica una formattazione del testo aggiuntiva (facoltativo)
 È possibile applicare una formattazione aggiuntiva al frammento di testo, come la sottolineatura, modificando le proprietà del file`TextState` oggetto.

```csharp
textFragment.TextState.Underline = true;
```

## Passaggio 8: salvare il documento PDF modificato
 Salvare il documento PDF modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Esempio di codice sorgente per Aggiungi testo con colori di ombreggiatura utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Crea un nuovo colore con lo spazio colore del motivo
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Conclusione
Hai aggiunto correttamente il testo con i colori di ombreggiatura al documento PDF utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.