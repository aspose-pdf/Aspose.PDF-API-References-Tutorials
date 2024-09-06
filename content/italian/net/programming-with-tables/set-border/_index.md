---
title: Imposta il bordo nel PDF nella tabella
linktitle: Imposta il bordo nel PDF nella tabella
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come impostare un bordo in un PDF in una tabella con Aspose.PDF per .NET.
type: docs
weight: 200
url: /it/net/programming-with-tables/set-border/
---
In questo tutorial, ti guideremo passo dopo passo nell'impostazione di un bordo in una tabella di un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

## Passaggio 1: creazione dell'istanza dell'oggetto Documento
Per prima cosa, creeremo un oggetto Document:

```csharp
Document doc = new Document();
```

## Passaggio 2: aggiunta di una pagina al documento PDF
Successivamente aggiungeremo una pagina al documento PDF:

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 3: creazione dell'oggetto BorderInfo
Ora creeremo un oggetto BorderInfo per definire il bordo della tabella:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Fase 4: Specificare i bordi superiore e inferiore
Specifichiamo che i bordi superiore e inferiore saranno doppi:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Passaggio 5: creazione dell'istanza dell'oggetto Tabella
Ora creiamo un oggetto Tabella:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Passaggio 6: Specificare la larghezza delle colonne
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
Successivamente aggiungeremo una cella alla riga:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Passaggio 9: Impostazione del bordo della cella
Definiremo il bordo della cella (doppio bordo):

```csharp
cell. Border = border;
```

## Passaggio 10: aggiunta della tabella alla pagina
Aggiungiamo ora la tabella alla pagina del documento:

```csharp
page.Paragraphs.Add(table);
```

## Passaggio 11: Salva il documento PDF
Infine, salveremo il documento PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per Set Border utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza dell'oggetto Documento
Document doc = new Document();
// Aggiungi pagina al documento PDF
Page page = doc.Pages.Add();
// Crea oggetto BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Specificare che il bordo superiore sarà doppio
border.Top.IsDoubled = true;
// Specificare che il bordo inferiore sarà doppio
border.Bottom.IsDoubled = true;
// Crea un'istanza dell'oggetto Tabella
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Specificare le informazioni sulla larghezza delle colonne
table.ColumnWidths = "100";
// Crea oggetto Riga
Aspose.Pdf.Row row = table.Rows.Add();
// Aggiungere una cella della tabella alla raccolta di celle della riga
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Imposta il bordo per l'oggetto cella (doppio bordo)
cell.Border = border;
// Aggiungi tabella alla raccolta di paragrafi della pagina
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Salva il documento PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Conclusione
Congratulazioni! Ora hai imparato come impostare un bordo in una tabella di un documento PDF usando Aspose.PDF per .NET. Questa guida passo passo ti ha mostrato come creare un documento, aggiungere una pagina, configurare il bordo della tabella e salvare il documento PDF. Ora puoi applicare questa conoscenza ai tuoi progetti.

### Domande frequenti

#### D: Posso impostare stili di bordo diversi (ad esempio, tratteggiato o punteggiato) per il bordo superiore e inferiore della tabella?

 A: Sì, puoi impostare stili di bordo diversi per i bordi superiore e inferiore della tabella modificando il`border.Top.Style` E`border.Bottom.Style`proprietà nel codice sorgente C# fornito. Aspose.PDF per .NET consente di scegliere tra vari stili di bordo, tra cui Solid, Dashed, Dotted, Double e altro ancora.

#### D: Come posso impostare il colore del bordo della tabella?

 A: Puoi impostare il colore del bordo della tabella modificando il`border.Color` proprietà nel codice sorgente C#. Basta fornire il colore desiderato, come`Aspose.Pdf.Color.Red` o qualsiasi altra rappresentazione cromatica valida, per personalizzare il colore del bordo.

#### D: È possibile applicare bordi a singole celle all'interno della tabella con impostazioni diverse (ad esempio, colori o stili di bordo diversi)?

 A: Sì, puoi applicare bordi a singole celle all'interno della tabella con impostazioni diverse configurando il`cell.Border` proprietà per ogni cella singolarmente. Ciò ti consente di avere stili e colori di bordo specifici per ogni cella in base alle tue esigenze.

#### D: Posso rimuovere il bordo da lati specifici della tabella (ad esempio, i bordi sinistro e destro)?

 A: Sì, puoi rimuovere il bordo da lati specifici della tabella modificando il`border.Left`, `border.Right`, `border.Top` , E`border.Bottom`proprietà nel codice sorgente C#. Impostando queste proprietà su`null` rimuoverà il bordo dai lati corrispondenti della tabella.

#### D: Come posso regolare lo spessore del bordo della tabella?

 A: È possibile regolare lo spessore del bordo della tabella modificando il`border.Width` proprietà nel codice sorgente C#. Imposta semplicemente la larghezza del bordo desiderata (in punti) per ottenere lo spessore desiderato.