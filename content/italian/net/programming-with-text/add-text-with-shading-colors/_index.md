---
title: Aggiungere testo con colori di ombreggiatura nel file PDF
linktitle: Aggiungere testo con colori di ombreggiatura nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere testo con colori di ombreggiatura in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-text/add-text-with-shading-colors/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di testo con colori di ombreggiatura in un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui vuoi aggiungere del testo con colori di ombreggiatura, aggiungi la seguente direttiva using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Passaggio 3: impostare la directory del documento
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: caricare il documento PDF
 Caricare il documento PDF esistente utilizzando`Document` costruttore e fornire il percorso al file del documento.

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

## Passaggio 6: imposta il colore di ombreggiatura per il testo
 Crea un nuovo`Color` oggetto con uno spazio colore pattern e specificare i colori di sfumatura del gradiente. Assegna questo colore al`ForegroundColor` proprietà del`TextState` del`TextFragment` oggetto.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Passaggio 7: applicare formattazione di testo aggiuntiva (facoltativo)
 È possibile applicare una formattazione aggiuntiva al frammento di testo, come la sottolineatura, modificando le proprietà del`TextState` oggetto.

```csharp
textFragment.TextState.Underline = true;
```

## Passaggio 8: salvare il documento PDF modificato
 Salvare il documento PDF modificato utilizzando`Save` metodo del`Document` oggetto.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Esempio di codice sorgente per aggiungere testo con colori di ombreggiatura utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Crea un nuovo colore con lo spazio colore del pattern
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Conclusione
Hai aggiunto con successo del testo con colori di ombreggiatura al tuo documento PDF usando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è l'obiettivo principale di questo tutorial?

R: Questo tutorial ti guida attraverso il processo di aggiunta di testo con colori di ombreggiatura a un file PDF utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari per ottenere questo risultato.

#### D: Quali namespace devo importare per questo tutorial?

A: Nel file di codice in cui vuoi aggiungere testo con colori di ombreggiatura, importa i seguenti namespace all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### D: Come faccio a specificare la directory dei documenti?

 A: Nel codice, individua la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come faccio a caricare un documento PDF esistente?

 A: Nel passaggio 4, caricherai un documento PDF esistente utilizzando`Document` costruttore e fornendo il percorso al file del documento:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Il codice va qui...
}
```

#### D: Come faccio a trovare e modificare un testo specifico all'interno del documento PDF?

 A: Nel passaggio 5, utilizzerai il`TextFragmentAbsorber` per trovare il testo desiderato all'interno del documento. Quindi, puoi modificarne le proprietà:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### D: Come posso impostare i colori di ombreggiatura per il testo?

 A: Nel passaggio 6, creerai un nuovo`Color` oggetto con uno spazio colore pattern e specificare i colori di sfumatura del gradiente. Assegna questo colore al`ForegroundColor` proprietà del`TextState` del`TextFragment` oggetto:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### D: Posso applicare una formattazione aggiuntiva al testo modificato?

A: Sì, nel passaggio 7, puoi applicare una formattazione di testo aggiuntiva, come la sottolineatura, modificando le proprietà del`TextState` oggetto:

```csharp
textFragment.TextState.Underline = true;
```

#### D: Come posso salvare il documento PDF modificato?

 A: Nel passaggio 8, salverai il documento PDF modificato utilizzando`Save` metodo del`Document` oggetto:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### D: Qual è la cosa più importante da imparare da questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come migliorare il tuo documento PDF aggiungendo testo con colori di ombreggiatura usando Aspose.PDF per .NET. Questo può essere particolarmente utile per evidenziare e mettere in risalto contenuti di testo specifici nei tuoi file PDF.