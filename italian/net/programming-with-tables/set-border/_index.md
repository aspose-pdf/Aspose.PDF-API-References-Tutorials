---
title: Imposta bordo
linktitle: Imposta bordo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come impostare un bordo in una tabella PDF con Aspose.PDF per .NET.
type: docs
weight: 200
url: /it/net/programming-with-tables/set-border/
---

In questo tutorial, ti guideremo passo dopo passo per impostare un bordo in una tabella di un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

## Passaggio 1: creazione di un'istanza dell'oggetto Document
Per prima cosa, creeremo un'istanza di un oggetto Document:

```csharp
Document doc = new Document();
```

## Passaggio 2: aggiunta di una pagina al documento PDF
Successivamente, aggiungeremo una pagina al documento PDF:

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 3: creazione dell'oggetto BorderInfo
Ora creeremo un oggetto BorderInfo per definire il bordo della tabella:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Passaggio 4: specificare i bordi superiore e inferiore
Specifichiamo che i bordi superiore e inferiore saranno doppi:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Passaggio 5: creazione di un'istanza dell'oggetto Table
Ora istanziamo un oggetto Table:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Passaggio 6: specificare la larghezza delle colonne
Specifichiamo le larghezze delle colonne della tabella:

```csharp
table. ColumnWidths = "100";
```

## Passaggio 7: creazione dell'oggetto riga
Creeremo un oggetto Row:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Passaggio 8: aggiunta di una cella alla riga
Successivamente, aggiungeremo una cella alla riga:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Passaggio 9: impostazione del bordo della cella
Definiremo il bordo della cella (doppio bordo):

```csharp
cell. Border = border;
```

## Passaggio 10: aggiunta della tabella alla pagina
Ora aggiungiamo la tabella alla pagina del documento:

```csharp
page.Paragraphs.Add(table);
```

## Passaggio 11: salva il documento PDF
Infine, salveremo il documento PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per Imposta bordo utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza dell'oggetto Document
Document doc = new Document();
// Aggiungi pagina al documento PDF
Page page = doc.Pages.Add();
// Crea un oggetto BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
// Specifica che il bordo superiore sarà doppio
border.Top.IsDoubled = true;
// Specifica che il bordo inferiore sarà doppio
border.Bottom.IsDoubled = true;
// Crea un'istanza dell'oggetto Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Specificare le informazioni sulla larghezza delle colonne
table.ColumnWidths = "100";
// Crea oggetto Riga
Aspose.Pdf.Row row = table.Rows.Add();
// Aggiungi una cella di tabella alla raccolta di righe di celle
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Imposta il bordo per l'oggetto cella (doppio bordo)
cell.Border = border;
//Aggiungi tabella alla raccolta di paragrafi di Page
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Salva il documento PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Conclusione
Congratulazioni! Ora hai imparato come impostare un bordo in una tabella di un documento PDF utilizzando Aspose.PDF per .NET. Questa guida dettagliata ti ha mostrato come creare un documento, aggiungere una pagina, configurare il bordo della tabella e salvare il documento PDF. Ora puoi applicare questa conoscenza ai tuoi progetti.