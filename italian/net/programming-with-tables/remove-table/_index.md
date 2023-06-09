---
title: Rimuovi tabella
linktitle: Rimuovi tabella
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come rimuovere una tabella in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 160
url: /it/net/programming-with-tables/remove-table/
---

In questo tutorial, ti guideremo passo dopo passo per rimuovere una tabella in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

## Passaggio 1: caricamento del documento PDF esistente
Innanzitutto, è necessario caricare il documento PDF esistente utilizzando il seguente codice:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento PDF esistente
Document pdfDocument = new Document(dataDir + "Table_input.pdf");
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
Per poter rimuovere la tabella, otterremo la prima tabella della pagina:

```csharp
// Ottieni la prima tabella sulla pagina
AbsorbedTable table = absorb.TableList[0];
```

## Passaggio 5: eliminazione della tabella
Ora rimuoviamo il tavolo usando l'assorbitore:

```csharp
//rimuovere il tavolo
absorb.Remove(table);
```

## Passaggio 6: salva il PDF
Infine, salviamo il documento PDF modificato:

```csharp
// Salva il PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

### Codice sorgente di esempio per Rimuovi tabella utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica il documento PDF esistente
Document pdfDocument = new Document(dataDir + "Table_input.pdf");

// Crea un oggetto TableAbsorber per trovare le tabelle
TableAbsorber absorber = new TableAbsorber();

// Visita la prima pagina con assorbitore
absorber.Visit(pdfDocument.Pages[1]);

// Ottieni il primo tavolo sulla pagina
AbsorbedTable table = absorber.TableList[0];

// Rimuovi il tavolo
absorber.Remove(table);

// Salva PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

## Conclusione
Congratulazioni! Ora hai imparato come rimuovere una tabella in un documento PDF utilizzando Aspose.PDF per .NET. Questa guida dettagliata ti ha mostrato come caricare il documento, trovare la tabella e rimuoverla. Ora puoi applicare questa conoscenza ai tuoi progetti.