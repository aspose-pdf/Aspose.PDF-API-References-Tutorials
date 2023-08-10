---
title: Aggiungi HTML usando DOM e sovrascrivi
linktitle: Aggiungi HTML usando DOM e sovrascrivi
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere contenuto HTML utilizzando DOM in Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-text/add-html-using-dom-and-overwrite/
---

Questo tutorial ti guiderà attraverso il processo di aggiunta di contenuto HTML utilizzando DOM (Document Object Model) in Aspose.PDF per .NET. Inoltre, imparerai come sovrascrivere gli stili per il contenuto HTML. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di disporre di quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato nel tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere il contenuto HTML, aggiungi le seguenti direttive using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory del documento e il percorso del file di output
 Nel codice, individuare la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 4: creare un nuovo oggetto documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione. Nel codice fornito, la nuova pagina è assegnata alla variabile`page`.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 6: creare un HtmlFragment con il contenuto HTML
Istanziare un`HtmlFragment` oggetto e fornire il contenuto HTML desiderato. Nel codice fornito, il contenuto HTML è assegnato alla variabile`title`. È possibile modificare il contenuto HTML secondo necessità.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Passaggio 7: sovrascrivi gli stili per il contenuto HTML
 Per sovrascrivere gli stili del contenuto HTML, puoi modificare il file`TextState` proprietà del`HtmlFragment` oggetto. Nel codice fornito, la famiglia di caratteri viene modificata in "Arial" e la dimensione del carattere è impostata su 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Passaggio 8: impostare le informazioni sul margine
Se necessario, regola i margini inferiore e superiore del frammento HTML. Nel codice fornito, il margine inferiore è impostato su 10 e il margine superiore è impostato su 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Passaggio 9: aggiungere HtmlFragment alla pagina
 Aggiungi il`HtmlFragment` opporsi alla raccolta di paragrafi della pagina.

```csharp
page.Paragraphs.Add(title);
```

## Passaggio 10: salvare il documento PDF
 Salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Specificare il percorso del file di output impostato nel passaggio 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Add HTMLUsing DOMAnd Overwrite using Aspose.PDF for .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza dell'oggetto Document
Document doc = new Document();
// Aggiungi una pagina alla raccolta di pagine di file PDF
Page page = doc.Pages.Add();
// Crea un'istanza di HtmlFragment con contnet HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//La famiglia di caratteri di "Verdana" verrà reimpostata su "Arial"
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Imposta le informazioni sul margine inferiore
title.Margin.Bottom = 10;
// Imposta le informazioni sul margine superiore
title.Margin.Top = 400;
// Aggiungi frammento HTML alla raccolta di paragrafi della pagina
page.Paragraphs.Add(title);
// Salva file PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Salva file PDF
doc.Save(dataDir);
```

## Conclusione
Hai aggiunto correttamente il contenuto HTML utilizzando DOM in Aspose.PDF per .NET e sovrascritto gli stili per il contenuto HTML. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.