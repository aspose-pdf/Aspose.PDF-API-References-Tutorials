---
title: Imposta bordo in PDF su tabella
linktitle: Imposta bordo in PDF su tabella
second_title: Aspose.PDF per riferimento API .NET
description: Ulteriori informazioni su come impostare un bordo in PDF al tavolo con Aspose.PDF per .NET.
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

### Esempio di codice sorgente per Imposta bordo utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza dell'oggetto Document
Document doc = new Document();
// Aggiungi pagina al documento PDF
Page page = doc.Pages.Add();
// Crea un oggetto BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Specifica che il bordo superiore sarà doppio
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
// Aggiungi tabella alla raccolta di paragrafi di Page
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Salva il documento PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Conclusione
Congratulazioni! Ora hai imparato come impostare un bordo in una tabella di un documento PDF utilizzando Aspose.PDF per .NET. Questa guida dettagliata ti ha mostrato come creare un documento, aggiungere una pagina, configurare il bordo della tabella e salvare il documento PDF. Ora puoi applicare questa conoscenza ai tuoi progetti.

### FAQ

#### D: Posso impostare diversi stili di bordo (ad es. tratteggiato o punteggiato) per i bordi superiore e inferiore della tabella?

 R: Sì, puoi impostare diversi stili di bordo per i bordi superiore e inferiore del tavolo modificando il file`border.Top.Style` E`border.Bottom.Style`properties nel codice sorgente C# fornito. Aspose.PDF per .NET ti consente di scegliere tra vari stili di bordo, inclusi Solido, Tratteggiato, Punteggiato, Doppio e altro.

#### D: Come posso impostare il colore del bordo del tavolo?

 R: Puoi impostare il colore del bordo del tavolo modificando il file`border.Color` proprietà nel codice sorgente C#. Basta fornire il colore desiderato, ad esempio`Aspose.Pdf.Color.Red` o qualsiasi altra rappresentazione cromatica valida, per personalizzare il colore del bordo.

#### D: È possibile applicare bordi a singole celle all'interno della tabella con impostazioni diverse (ad es. colori o stili di bordo diversi)?

 R: Sì, puoi applicare i bordi alle singole celle all'interno della tabella con impostazioni diverse configurando il file`cell.Border` proprietà per ogni cella individualmente. Ciò ti consente di avere stili e colori del bordo specifici della cella in base alle tue esigenze.

#### D: Posso rimuovere il bordo da lati specifici del tavolo (ad es. bordi sinistro e destro)?

 R: Sì, puoi rimuovere il bordo da lati specifici del tavolo modificando il file`border.Left`, `border.Right`, `border.Top` , E`border.Bottom`proprietà nel codice sorgente C#. Impostando queste proprietà su`null` rimuoverà il bordo dai lati corrispondenti della tabella.

#### D: Come posso regolare lo spessore del bordo del tavolo?

 R: Puoi regolare lo spessore del bordo del tavolo modificando il file`border.Width` proprietà nel codice sorgente C#. Basta impostare la larghezza del bordo desiderata (in punti) per ottenere lo spessore desiderato.