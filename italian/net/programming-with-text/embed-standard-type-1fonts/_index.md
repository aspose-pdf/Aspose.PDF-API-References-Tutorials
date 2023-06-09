---
title: Incorpora font di tipo 1 standard
linktitle: Incorpora font di tipo 1 standard
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come incorporare i caratteri standard di tipo 1 in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 140
url: /it/net/programming-with-text/embed-standard-type-1fonts/
---

Questo tutorial ti guiderà attraverso il processo di incorporamento dei caratteri standard di tipo 1 in un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di disporre di quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato nel tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri incorporare i font Type 1 standard, aggiungi la seguente direttiva using all'inizio del file:

```csharp
using Aspose.Pdf;
```

## Passaggio 3: impostare la directory dei documenti
 Nel codice, individuare la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i documenti.

## Passaggio 4: caricare il documento PDF esistente
 Carica un documento PDF esistente utilizzando il file`Document` costruttore e passando il percorso al file PDF di input.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Passaggio 5: impostare la proprietà EmbedStandardFonts
 Impostare il`EmbedStandardFonts` proprietà del documento a`true` per abilitare l'incorporamento di font Type 1 standard.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## Passaggio 6: incorpora i caratteri in ogni pagina
 Scorri ogni pagina del documento PDF e controlla se i caratteri sono già incorporati. In caso contrario, impostare il`IsEmbedded` proprietà a`true` per incorporare il carattere.

```csharp
foreach(Page page in pdfDocument.Pages)
{
     if (page.Resources.Fonts != null)
     {
         foreach(Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
         {
             if (!pageFont.IsEmbedded)
             {
                 pageFont.IsEmbedded = true;
             }
         }
     }
}
```

## Passaggio 7: salvare il documento PDF aggiornato
 Salva il documento PDF aggiornato utilizzando il file`Save` metodo del`Document` oggetto, specificando il percorso del file di output.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Esempio di codice sorgente per Embed Standard Type 1Fonts utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica un documento PDF esistente
Document pdfDocument = new Document(dataDir + "input.pdf");
// Imposta la proprietà EmbedStandardFonts del documento
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Controlla se il carattere è già incorporato
			if (!pageFont.IsEmbedded)
			{
				pageFont.IsEmbedded = true;
			}
		}
	}
}
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

## Conclusione
Hai incorporato correttamente i caratteri standard di tipo 1 in un documento PDF utilizzando Aspose.PDF per .NET. Il file PDF aggiornato con i caratteri incorporati è stato salvato nel percorso del file di output specificato.