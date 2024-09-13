---
title: Aggiungere HTML utilizzando DOM e sovrascrittura PDF
linktitle: Aggiungi HTML usando DOM e sovrascrivi
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere contenuto HTML utilizzando DOM e sovrascrittura PDF in Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di contenuto HTML tramite DOM (Document Object Model) in Aspose.PDF per .NET. Inoltre, imparerai come sovrascrivere gli stili per il contenuto HTML. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui vuoi aggiungere il contenuto HTML, aggiungi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory del documento e il percorso del file di output
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 4: creare un nuovo oggetto Documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: aggiungere una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando il`Add` metodo del`Pages` raccolta. Nel codice fornito, la nuova pagina è assegnata alla variabile`page`.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 6: creare un HtmlFragment con il contenuto HTML
 Crea un'istanza`HtmlFragment` oggetto e fornire il contenuto HTML desiderato. Nel codice fornito, il contenuto HTML è assegnato alla variabile`title`È possibile modificare il contenuto HTML in base alle proprie esigenze.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Passaggio 7: sovrascrivere gli stili per il contenuto HTML
 Per sovrascrivere gli stili del contenuto HTML, puoi modificare`TextState` proprietà del`HtmlFragment` oggetto. Nel codice fornito, la famiglia di font è cambiata in "Arial" e la dimensione del font è impostata su 20.

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
 Aggiungere il`HtmlFragment` oggetto alla raccolta di paragrafi della pagina.

```csharp
page.Paragraphs.Add(title);
```

## Passaggio 10: Salvare il documento PDF
 Salvare il documento PDF utilizzando`Save` metodo del`Document` oggetto. Specifica il percorso del file di output impostato nel passaggio 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Aggiungi HTMLUsando DOMAnd Sovrascrivi usando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza dell'oggetto Documento
Document doc = new Document();
// Aggiungi una pagina alla raccolta di pagine del file PDF
Page page = doc.Pages.Add();
// Crea un'istanza di HtmlFragment con contenuti HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//La famiglia di caratteri da 'Verdana' verrà reimpostata su 'Arial'
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
Hai aggiunto con successo contenuto HTML usando DOM in Aspose.PDF per .NET e hai sovrascritto gli stili per il contenuto HTML. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è l'obiettivo di questo tutorial?

R: Questo tutorial è progettato per guidarti attraverso il processo di aggiunta di contenuto HTML a un documento PDF utilizzando il Document Object Model (DOM) in Aspose.PDF per .NET. Inoltre, imparerai come sovrascrivere gli stili per il contenuto HTML, consentendoti di personalizzarne l'aspetto. Il tutorial fornisce frammenti di codice sorgente C# per dimostrare i passaggi richiesti.

#### D: Quali namespace devo importare per questo tutorial?

A: Nel file di codice in cui intendi aggiungere contenuto HTML, importa i seguenti namespace all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### D: Come faccio a specificare la directory del documento e il percorso del file di output?

 A: Nel codice, individua la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come si crea un oggetto Documento?

 A: Nel passaggio 4, creerai un nuovo`Document` oggetto utilizzando la seguente riga di codice:

```csharp
Document doc = new Document();
```

#### D: Come posso aggiungere una pagina al documento?

 A: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando`Add` metodo del`Pages` collezione:

```csharp
Page page = doc.Pages.Add();
```

#### D: Come posso impostare il contenuto HTML utilizzando il DOM?

 A: Nel passaggio 6, creerai un`HtmlFragment` oggetto e assegnargli il contenuto HTML desiderato. Il contenuto HTML viene assegnato alla variabile`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### D: Come posso sovrascrivere gli stili del contenuto HTML?

 A: Nel passaggio 7, sovrascriverai gli stili del contenuto HTML modificando il`TextState` proprietà del`HtmlFragment`oggetto. Ad esempio, puoi cambiare la famiglia di font in "Arial" e impostare la dimensione del font su 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### D: Posso modificare il margine del contenuto HTML?

R: Sì, nel passaggio 8 puoi modificare i margini inferiore e superiore del frammento HTML in base alle tue esigenze:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### D: Come posso aggiungere HtmlFragment al documento PDF?

 A: Nel passaggio 9, aggiungerai il`HtmlFragment` oggetto (`title`) alla raccolta di paragrafi della pagina:

```csharp
page.Paragraphs.Add(title);
```

#### D: Come posso salvare il documento PDF risultante?

 A: Dopo aver aggiunto il contenuto HTML e aver personalizzato i suoi stili, utilizzare`Save` metodo del`Document` oggetto per salvare il documento PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### D: Qual è il messaggio più importante da trarre da questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come incorporare contenuti HTML usando il Document Object Model (DOM) in Aspose.PDF per .NET. Inoltre, hai acquisito la capacità di sovrascrivere gli stili per personalizzare l'aspetto del contenuto HTML nel documento PDF risultante.