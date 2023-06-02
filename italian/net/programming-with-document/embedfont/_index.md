---
title: Incorpora carattere
linktitle: Incorpora carattere
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come incorporare i caratteri in un file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata. Assicurati che i tuoi documenti siano visualizzati correttamente su qualsiasi dispositivo.
type: docs
weight: 120
url: /it/net/programming-with-document/embedfont/
---

In questo tutorial, discuteremo come incorporare i caratteri in un file PDF utilizzando Aspose.PDF per .NET. Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, modificare e manipolare documenti PDF in modo programmatico. Questa libreria offre un'ampia gamma di funzionalità per lavorare con i documenti PDF, inclusa l'aggiunta di testo, immagini, tabelle e molto altro. L'incorporamento di caratteri in un file PDF è un requisito comune per gli sviluppatori che desiderano assicurarsi che il file PDF venga visualizzato correttamente su dispositivi diversi, indipendentemente dal fatto che i caratteri richiesti siano installati o meno su tali dispositivi.

## Passaggio 1: creare una nuova applicazione console C#
Per iniziare, crea una nuova applicazione console C# in Visual Studio. Puoi chiamarlo come preferisci. Una volta creato il progetto, è necessario aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa lo spazio dei nomi Aspose.PDF
Aggiungi la seguente riga di codice nella parte superiore del file C# per importare lo spazio dei nomi Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Passaggio 3: caricare un file PDF esistente
Per incorporare i font in un file PDF esistente, è necessario caricare quel file utilizzando la classe Document. Il codice seguente mostra come caricare un file PDF esistente:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica un file PDF esistente
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 4: scorrere tutte le pagine
Dopo aver caricato il file PDF, è necessario scorrere tutte le pagine del documento. Per ogni pagina, è necessario verificare se vengono utilizzati caratteri e, in tal caso, è necessario incorporare tali caratteri. Il codice seguente mostra come scorrere tutte le pagine nel file PDF e incorporare i caratteri:

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            // Controlla se il carattere è già incorporato
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    // Controlla gli oggetti Form
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                // Controlla se il carattere è incorporato
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## Passaggio 5: salvare il documento PDF
Una volta incorporati tutti i caratteri nel file PDF, è necessario salvare il documento. Il codice seguente mostra come salvare il file PDF:

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// Salva documento PDF
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### Codice sorgente di esempio per incorporare il carattere utilizzando Aspose.PDF per .NET

Ecco il codice sorgente completo per incorporare un font utilizzando Aspose.PDF per .NET.


```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Carica un file PDF esistente
Document doc = new Document(dataDir + "input.pdf");

// Scorri tutte le pagine
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Controlla se il carattere è già incorporato
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	// Controlla gli oggetti Form
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				// Controlla se il carattere è incorporato
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
// Salva documento PDF
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## Conclusione
In questo articolo, abbiamo discusso su come incorporare i caratteri in un file PDF utilizzando Aspose.PDF per .NET. Aspose.PDF per .NET fornisce un'API semplice e facile da usare per lavorare con documenti PDF, inclusa l'aggiunta e l'incorporamento di caratteri. L'incorporamento dei caratteri in un file PDF è un passaggio importante per garantire che il documento venga visualizzato correttamente su dispositivi diversi, indipendentemente dal fatto che i caratteri richiesti siano installati su tali dispositivi
