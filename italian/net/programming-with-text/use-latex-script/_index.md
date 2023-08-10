---
title: Usa lo script in lattice
linktitle: Usa lo script in lattice
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare lo script Latex per aggiungere espressioni o formule matematiche in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 550
url: /it/net/programming-with-text/use-latex-script/
---

Questo tutorial spiega come utilizzare lo script Latex per aggiungere espressioni o formule matematiche in un documento PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi per creare un documento, aggiungere una tabella con una cella contenente lo script LaTeX e salvare il documento.

## Prerequisiti

Prima di iniziare, assicurati di disporre di quanto segue:

- Conoscenza base del linguaggio di programmazione C#.
- Aspose.PDF per la libreria .NET installata. Puoi ottenerlo dal sito Web di Aspose o utilizzare NuGet per installarlo nel tuo progetto.

## Passaggio 1: impostare il progetto

Crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi necessari

Aggiungi le seguenti direttive using all'inizio del tuo file C# per importare gli spazi dei nomi richiesti:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Tables;
using Aspose.Pdf.Text;
```

## Passaggio 3: creare e configurare il documento

 Crea un nuovo`Document` oggetto e aggiungi una pagina ad esso:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Passaggio 4: creare e configurare la tabella

Crea una tabella e aggiungi una riga ad essa:

```csharp
Table table = new Table();
Row row = table.Rows.Add();
```

## Passaggio 5: aggiungi una cella con lo script LaTeX

 Crea una cella e aggiungi a`LatexFragment` contenente lo script Latex:

```csharp
string latexText1 = "$123456789+\\sqrt{1}+\\int_a^b f(x)dx$";
Cell cell = row.Cells.Add();
LatexFragment ltext1 = new LatexFragment(latexText1, true);
cell.Paragraphs.Add(ltext1);
```

 Si noti che il`true` parametro in`LatexFragment` costruttore elimina i rientri di paragrafo Latex.

## Passaggio 6: aggiungi la tabella alla pagina

Aggiungi la tabella alla pagina:

```csharp
page.Paragraphs.Add(table);
```

## Passaggio 7: salvare il documento

Salva il documento in un file PDF:

```csharp
doc.Save(dataDir + "LatextScriptInPdf_out.pdf");
```

### Esempio di codice sorgente per Use Latex Script using Aspose.PDF for .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un nuovo oggetto documento
Document doc = new Document();
//Aggiungi pagina nella raccolta di pagine
Page page = doc.Pages.Add();
// Crea una tabella
Table table = new Table();
// Aggiungi una riga nella tabella
Row row = table.Rows.Add();
// Aggiungi cella con script in lattice per aggiungere espressioni/formule metamatiche
string latexText1 = "$123456789+\\sqrt{1}+\\int_a^b f(x)dx$";
Cell cell = row.Cells.Add();
cell.Margin = new MarginInfo { Left = 20, Right = 20, Top = 20, Bottom = 20 };
// Il secondo parametro bool del costruttore LatexFragment fornisce l'eliminazione dei rientri di paragrafo LaTeX.
LatexFragment ltext1 = new LatexFragment(latexText1, true);
cell.Paragraphs.Add(ltext1);
// Aggiungi tabella all'interno della pagina
page.Paragraphs.Add(table);
// Salva il documento
doc.Save(dataDir + "LatextScriptInPdf_out.pdf");
```

## Conclusione

Congratulazioni! Hai imparato con successo come utilizzare lo script Latex per aggiungere espressioni o formule matematiche in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito istruzioni dettagliate sulla creazione di un documento, l'aggiunta di una tabella con una cella contenente lo script LaTeX e il salvataggio del documento. Ora puoi incorporare questo codice nei tuoi progetti C# per generare file PDF con contenuto matematico.