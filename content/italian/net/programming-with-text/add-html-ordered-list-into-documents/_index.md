---
title: Aggiungi elenco ordinato HTML nei documenti
linktitle: Aggiungi elenco ordinato HTML nei documenti
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere un elenco ordinato HTML a un documento utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-text/add-html-ordered-list-into-documents/
---
In questo tutorial imparerai come utilizzare la libreria Aspose.PDF per .NET per aggiungere un elenco ordinato HTML in un documento. Il codice fornito illustra i passaggi necessari per eseguire questa attività.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere l'elenco ordinato HTML, aggiungi le seguenti direttive using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory del documento e il percorso del file di output
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

 Quindi, individua la riga che dice`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` e sostituire`"AddHTMLOrderedListIntoDocuments_out.pdf"` con il nome desiderato per il file PDF di output.

## Passaggio 4: crea un nuovo oggetto Documento
 Istanziarne uno nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: crea un oggetto HtmlFragment con il contenuto HTML
 Istanziare un`HtmlFragment` oggetto con il contenuto HTML che desideri aggiungere al documento. Nel codice fornito, il contenuto HTML viene assegnato alla variabile`t`. È possibile modificare il contenuto HTML secondo necessità.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Passaggio 6: aggiungi una pagina al documento
 Aggiungi una nuova pagina al documento utilizzando il file`Add` metodo del`Pages`collezione. Nel codice fornito, la nuova pagina viene assegnata alla variabile`page`.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 7: aggiungi HtmlFragment alla pagina
 Aggiungi il`HtmlFragment` opporsi alla pagina utilizzando il comando`Add` metodo del`Paragraphs` collezione.

```csharp
page.Paragraphs.Add(t);
```

## Passaggio 8: salva il documento PDF
 Salvare il file PDF risultante utilizzando il file`Save` metodo del`Document` oggetto. Specificare il percorso del file di output impostato al passaggio 3.

```csharp
doc.Save(outFile);
```

### Codice sorgente di esempio per aggiungere elenco ordinato HTML nei documenti utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Il percorso del documento di output.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Istanziare l'oggetto Documento
Document doc = new Document();
// Crea un'istanza dell'oggetto HtmlFragment con il frammento HTML corrispondente
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Aggiungi pagina nella raccolta Pagine
Page page = doc.Pages.Add();
// Aggiungi HtmlFragment all'interno della pagina
page.Paragraphs.Add(t);
// Salva il file PDF risultante
doc.Save(outFile);
```

## Conclusione
Hai aggiunto con successo un elenco ordinato HTML in un documento utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

Ricordati di personalizzare il contenuto HTML e adattare il codice in base alle tue esigenze specifiche.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

R: Questo tutorial ha lo scopo di guidarti attraverso il processo di aggiunta di un elenco ordinato HTML in un documento utilizzando la libreria Aspose.PDF per .NET. Fornisce istruzioni dettagliate e frammenti di codice per aiutarti a raggiungere questo compito.

#### D: Quali spazi dei nomi devo importare per questo tutorial?

R: Devi importare i seguenti spazi dei nomi nella parte superiore del file di codice:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### D: Come posso specificare la directory del documento e il percorso del file di output?

 A: Nel codice, individuare la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti. Inoltre, trova la linea`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` e sostituire`"AddHTMLOrderedListIntoDocuments_out.pdf"` con il nome del file PDF di output desiderato.

#### D: Posso personalizzare il contenuto HTML da aggiungere al documento?

 R: Assolutamente! Nel passaggio 5 creerai un file`HtmlFragment` oggetto nominato`t` che contiene il contenuto HTML. Puoi modificare il contenuto HTML all'interno dei backtick in base alle tue esigenze.

#### D: Come posso aggiungere l'elenco ordinato HTML a una pagina del documento?

 R: Nel passaggio 7, aggiungerai il file`HtmlFragment` oggetto (`t` ) alla pagina utilizzando il file`Add` metodo del`Paragraphs`collezione. Ciò integrerà perfettamente l'elenco ordinato HTML nel documento.

#### D: Come posso salvare il documento PDF risultante?

 R: Dopo aver aggiunto il contenuto HTML e averlo disposto su una pagina, puoi salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Assicurati di fornire il percorso corretto del file di output impostato in precedenza.

#### D: Potete fornire un riepilogo del codice sorgente di esempio come riferimento?

R: Certamente! Ecco una versione riepilogativa del codice sorgente di esempio fornito in questo tutorial:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### D: Qual è il punto chiave di questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come sfruttare la libreria Aspose.PDF per .NET per incorporare un elenco ordinato HTML in un documento. Questa nuova conoscenza può essere applicata per migliorare i processi di creazione e manipolazione dei documenti.