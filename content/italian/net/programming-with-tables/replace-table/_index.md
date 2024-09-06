---
title: Sostituisci tabella nel documento PDF
linktitle: Sostituisci tabella nel documento PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come sostituire una tabella in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 180
url: /it/net/programming-with-tables/replace-table/
---
In questo tutorial, ti guideremo passo dopo passo nella sostituzione di una tabella in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

## Passaggio 1: caricamento del documento PDF esistente
Per prima cosa, è necessario caricare il documento PDF esistente utilizzando il seguente codice:

```csharp
// Percorso alla directory dei documenti
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

## Passaggio 3: Visita la prima pagina con l'assorbitore
Visiteremo ora la prima pagina del documento PDF utilizzando l'assorbitore:

```csharp
// Visita la prima pagina con l'assorbitore
absorb.Visit(pdfDocument.Pages[1]);
```

## Fase 4: Ottenere la prima tabella sulla pagina
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

## Fase 6: Sostituzione della tabella esistente con la nuova tabella
Ora sostituiremo la tabella esistente con la nuova tabella nella prima pagina del documento:

```csharp
// Sostituisci la tabella con la nuova tabella
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Fase 7: Salvataggio del documento
Infine, salviamo il documento PDF modificato:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Esempio di codice sorgente per Replace Table utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica documento PDF esistente
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Crea un oggetto TableAbsorber per trovare le tabelle
TableAbsorber absorber = new TableAbsorber();

// Visita la prima pagina con l'assorbitore
absorber.Visit(pdfDocument.Pages[1]);

// Ottieni la prima tabella sulla pagina
AbsorbedTable table = absorber.TableList[0];

// Crea nuova tabella
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// Sostituisci il tavolo con uno nuovo
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// Salvare il documento
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## Conclusione
Congratulazioni! Ora hai imparato come sostituire una tabella in un documento PDF usando Aspose.PDF per .NET. Questa guida passo passo ti ha mostrato come caricare il documento, trovare la tabella esistente, creare una nuova tabella e sostituirla. Ora puoi applicare questa conoscenza ai tuoi progetti.

### FAQ per sostituire la tabella nel documento PDF

#### D: Posso sostituire più tabelle nello stesso documento PDF utilizzando questo approccio?

 R: Sì, puoi sostituire più tabelle nello stesso documento PDF seguendo lo stesso procedimento per ogni tabella che vuoi sostituire. Dopo aver ottenuto il`AbsorbedTable` oggetto per ogni tabella utilizzando il`TableAbsorber` , puoi creare nuove tabelle corrispondenti e quindi utilizzare il`absorber.Replace()` metodo per sostituire ogni tabella esistente con la rispettiva nuova tabella.

#### D: Cosa succede se la nuova tabella ha un numero di colonne diverso rispetto alla tabella originale?

R: Se la nuova tabella ha un numero di colonne diverso da quello della tabella originale, potrebbe verificarsi un comportamento imprevisto o problemi di layout nel documento PDF modificato. È essenziale assicurarsi che la struttura della nuova tabella (numero di colonne e relative larghezze) corrisponda alla struttura della tabella originale per una sostituzione senza soluzione di continuità.

#### D: Posso sostituire una tabella su una pagina specifica diversa dalla prima?

 A: Sì, puoi sostituire una tabella su una pagina specifica diversa dalla prima pagina modificando l'indice della pagina in`pdfDocument.Pages[]` chiamata del metodo quando si ottiene il`AbsorbedTable` oggetto. Ad esempio, per sostituire una tabella nella seconda pagina, dovresti usare`pdfDocument.Pages[2]`.

#### D: Posso personalizzare l'aspetto della nuova tabella, ad esempio aggiungendo un colore di sfondo o dei bordi?

 A: Sì, puoi personalizzare l'aspetto della nuova tabella impostando varie proprietà della`Table` e le sue celle. Ad esempio, puoi impostare`BackgroundColor` proprietà delle celle per aggiungere colore di sfondo. Puoi anche impostare la`DefaultCellBorder` proprietà della nuova tabella o delle singole celle a cui aggiungere bordi.

#### D: La sostituzione di una tabella influisce sul layout del contenuto del resto del documento PDF?

R: La sostituzione di una tabella può influire sul layout del contenuto se le dimensioni o la struttura della nuova tabella differiscono in modo significativo dalla tabella originale. Il resto del contenuto sulla pagina verrà riadattato per adattarsi alla nuova tabella. È essenziale progettare attentamente la nuova tabella in modo che si adatti perfettamente al layout esistente per evitare problemi di layout.