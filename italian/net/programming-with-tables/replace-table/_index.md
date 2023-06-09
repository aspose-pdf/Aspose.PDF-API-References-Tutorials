---
title: Sostituisci tabella
linktitle: Sostituisci tabella
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come sostituire una tabella in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 180
url: /it/net/programming-with-tables/replace-table/
---

In questo tutorial, ti guideremo passo dopo passo per sostituire una tabella in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

## Passaggio 1: caricamento del documento PDF esistente
Innanzitutto, è necessario caricare il documento PDF esistente utilizzando il seguente codice:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento PDF esistente
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## Passaggio 2: creazione dell'oggetto TableAbsorber per trovare le tabelle
Successivamente, creeremo un oggetto TableAbsorber per trovare le tabelle nel documento PDF:

```csharp
// Crea un oggetto TableAbsorber per trovare le tabelle
TableAbsorber absorber = new TableAbsorber();
```

## Passaggio 3: visita la prima pagina con l'assorbitore
Visiteremo ora la prima pagina del documento PDF utilizzando l'assorbitore:

```csharp
// Visita la prima pagina con l'assorbitore
absorb.Visit(pdfDocument.Pages[1]);
```

## Passaggio 4: ottenere la prima tabella sulla pagina
Per poter sostituire la tabella, otterremo la prima tabella della pagina:

```csharp
// Ottieni la prima tabella sulla pagina
AbsorbedTable table = absorb.TableList[0];
```

## Passaggio 5: creazione di una nuova tabella
Ora creeremo una nuova tabella con le colonne e le celle desiderate:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## Passaggio 6: sostituzione della tabella esistente con la nuova tabella
Ora sostituiremo la tabella esistente con la nuova tabella nella prima pagina del documento:

```csharp
// Sostituisci la tabella con la nuova tabella
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Passaggio 7: salvare il documento
Infine, salviamo il documento PDF modificato:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Esempio di codice sorgente per Sostituisci tabella utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica il documento PDF esistente
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Crea un oggetto TableAbsorber per trovare le tabelle
TableAbsorber absorber = new TableAbsorber();

// Visita la prima pagina con assorbitore
absorber.Visit(pdfDocument.Pages[1]);

// Ottieni il primo tavolo sulla pagina
AbsorbedTable table = absorber.TableList[0];

// Crea nuova tabella
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// Sostituisci la tabella con una nuova
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// Salva documento
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## Conclusione
Congratulazioni! Ora hai imparato come sostituire una tabella in un documento PDF utilizzando Aspose.PDF per .NET. Questa guida dettagliata ti ha mostrato come caricare il documento, trovare la tabella esistente, creare una nuova tabella e sostituirla. Ora puoi applicare questa conoscenza ai tuoi progetti.