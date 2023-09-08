---
title: Aggiungi HTML utilizzando DOM e sovrascrivi PDF
linktitle: Aggiungi HTML utilizzando DOM e sovrascrivi
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere contenuto HTML utilizzando DOM e sovrascrittura PDF in Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di contenuto HTML utilizzando DOM (Document Object Model) in Aspose.PDF per .NET. Inoltre, imparerai come sovrascrivere gli stili per il contenuto HTML. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
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
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 4: crea un nuovo oggetto Documento
 Istanziarne uno nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungi una nuova pagina al documento utilizzando il file`Add` metodo del`Pages`collezione. Nel codice fornito, la nuova pagina viene assegnata alla variabile`page`.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 6: crea un HtmlFragment con il contenuto HTML
 Istanziare un`HtmlFragment` oggetto e fornire il contenuto HTML desiderato. Nel codice fornito, il contenuto HTML viene assegnato alla variabile`title`. È possibile modificare il contenuto HTML secondo necessità.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Passaggio 7: sovrascrivi gli stili per il contenuto HTML
 Per sovrascrivere gli stili del contenuto HTML, è possibile modificare il file`TextState` proprietà del`HtmlFragment` oggetto. Nel codice fornito, la famiglia di caratteri viene modificata in "Arial" e la dimensione del carattere è impostata su 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Passaggio 8: impostare le informazioni sui margini
Se necessario, regola i margini inferiore e superiore del frammento HTML. Nel codice fornito, il margine inferiore è impostato su 10 e il margine superiore è impostato su 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Passaggio 9: aggiungi HtmlFragment alla pagina
 Aggiungi il`HtmlFragment` opporsi alla raccolta di paragrafi della pagina.

```csharp
page.Paragraphs.Add(title);
```

## Passaggio 10: salva il documento PDF
 Salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Specificare il percorso del file di output impostato al passaggio 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Codice sorgente di esempio per Aggiungi HTML utilizzando DOM e sovrascrivi utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Istanziare l'oggetto Documento
Document doc = new Document();
// Aggiungi una raccolta di pagine a pagine di file PDF
Page page = doc.Pages.Add();
// Crea un'istanza di HtmlFragment con reti HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//La famiglia di caratteri di "Verdana" verrà reimpostata su "Arial"
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Imposta le informazioni sul margine inferiore
title.Margin.Bottom = 10;
// Imposta le informazioni sul margine superiore
title.Margin.Top = 400;
// Aggiungi un frammento HTML alla raccolta di paragrafi della pagina
page.Paragraphs.Add(title);
// Salva file PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Salva file PDF
doc.Save(dataDir);
```

## Conclusione
Hai aggiunto con successo contenuto HTML utilizzando DOM in Aspose.PDF per .NET e sovrascritto gli stili per il contenuto HTML. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è il focus di questo tutorial?

R: Questo tutorial è progettato per guidarti attraverso il processo di aggiunta di contenuto HTML a un documento PDF utilizzando il Document Object Model (DOM) in Aspose.PDF per .NET. Inoltre, imparerai come sovrascrivere gli stili per il contenuto HTML, permettendoti di personalizzarne l'aspetto. L'esercitazione fornisce frammenti di codice sorgente C# per dimostrare i passaggi richiesti.

#### D: Quali spazi dei nomi devo importare per questo tutorial?

R: Nel file di codice in cui intendi aggiungere contenuto HTML, importa i seguenti spazi dei nomi all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### D: Come posso specificare la directory del documento e il percorso del file di output?

 A: Nel codice, individuare la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso creare un oggetto Document?

 R: Nel passaggio 4 creerai un'istanza di new`Document` oggetto utilizzando la seguente riga di codice:

```csharp
Document doc = new Document();
```

#### D: Come faccio ad aggiungere una pagina al documento?

 R: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione:

```csharp
Page page = doc.Pages.Add();
```

#### D: Come posso impostare il contenuto HTML utilizzando il DOM?

 R: Nel passaggio 6 creerai un file`HtmlFragment` oggetto e assegnargli il contenuto HTML desiderato. Il contenuto HTML viene assegnato alla variabile`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### D: Come posso sovrascrivere gli stili del contenuto HTML?

 R: Nel passaggio 7, sovrascriverai gli stili del contenuto HTML modificando il file`TextState` proprietà del`HtmlFragment` oggetto. Ad esempio, puoi modificare la famiglia di caratteri in "Arial" e impostare la dimensione del carattere su 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### D: Posso regolare il margine del contenuto HTML?

R: Sì, al passaggio 8 puoi regolare i margini inferiore e superiore del frammento HTML secondo necessità:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### D: Come posso aggiungere HtmlFragment al documento PDF?

 R: Nel passaggio 9 aggiungerai il file`HtmlFragment` oggetto (`title`) alla raccolta paragrafi della pagina:

```csharp
page.Paragraphs.Add(title);
```

#### D: Come posso salvare il documento PDF risultante?

 R: Dopo aver aggiunto il contenuto HTML e personalizzato i suoi stili, utilizza il file`Save` metodo del`Document` oggetto per salvare il documento PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### D: Qual è il punto chiave di questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come incorporare contenuto HTML utilizzando il Document Object Model (DOM) in Aspose.PDF per .NET. Inoltre, hai acquisito la possibilità di sovrascrivere gli stili per personalizzare l'aspetto del contenuto HTML all'interno del documento PDF risultante.