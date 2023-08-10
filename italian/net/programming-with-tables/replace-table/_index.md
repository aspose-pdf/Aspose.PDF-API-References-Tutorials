---
title: Sostituisci tabella nel documento PDF
linktitle: Sostituisci tabella nel documento PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come sostituire una tabella nel documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 180
url: /it/net/programming-with-tables/replace-table/
---
In questo tutorial, ti guideremo passo dopo passo per sostituire una tabella nel documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

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

### Domande frequenti per sostituire la tabella nel documento PDF

#### D: Posso sostituire più tabelle nello stesso documento PDF utilizzando questo approccio?

 R: Sì, puoi sostituire più tabelle nello stesso documento PDF seguendo la stessa procedura per ogni tabella che desideri sostituire. Dopo aver ottenuto il`AbsorbedTable` oggetto per ogni tabella utilizzando il`TableAbsorber` , è possibile creare nuove tabelle corrispondenti e quindi utilizzare il file`absorber.Replace()` metodo per sostituire ogni tabella esistente con la rispettiva nuova tabella.

#### D: Cosa succede se la nuova tabella ha un numero di colonne diverso rispetto alla tabella originale?

R: Se la nuova tabella ha un numero di colonne diverso rispetto alla tabella originale, potrebbe verificarsi un comportamento imprevisto o problemi di layout nel documento PDF modificato. È essenziale garantire che la struttura della nuova tabella (numero di colonne e relative larghezze) corrisponda alla struttura della tabella originale per una sostituzione perfetta.

#### D: Posso sostituire una tabella su una pagina specifica diversa dalla prima pagina?

 R: Sì, puoi sostituire una tabella su una pagina specifica diversa dalla prima pagina modificando l'indice della pagina nel file`pdfDocument.Pages[]` chiamata al metodo quando si ottiene il`AbsorbedTable` oggetto. Ad esempio, per sostituire una tabella nella seconda pagina, useresti`pdfDocument.Pages[2]`.

#### D: Posso personalizzare l'aspetto della nuova tabella, ad esempio aggiungendo il colore di sfondo o i bordi?

 R: Sì, puoi personalizzare l'aspetto della nuova tabella impostando varie proprietà del file`Table` e le sue cellule. Ad esempio, puoi impostare il`BackgroundColor` proprietà delle celle per aggiungere il colore di sfondo. Puoi anche impostare il`DefaultCellBorder` proprietà della nuova tabella o delle singole celle per aggiungere i bordi.

#### D: La sostituzione di una tabella influisce sul layout del contenuto del resto del documento PDF?

R: La sostituzione di una tabella può influire sul layout del contenuto se le dimensioni o la struttura della nuova tabella differiscono in modo significativo dalla tabella originale. Il resto del contenuto della pagina verrà ridisposto per adattarsi alla nuova tabella. È essenziale progettare attentamente il nuovo tavolo in modo che si adatti perfettamente al layout esistente per evitare problemi di layout.