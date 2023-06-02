---
title: Rimuovi più tabelle
linktitle: Rimuovi più tabelle
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come rimuovere più tabelle in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 150
url: /it/net/programming-with-tables/remove-multiple-tables/
---

In questo tutorial, ti guideremo passo dopo passo per rimuovere più tabelle in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

## Passaggio 1: caricamento del documento PDF esistente
Innanzitutto, è necessario caricare il documento PDF esistente utilizzando il seguente codice:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento PDF esistente
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");
```

## Passaggio 2: creazione dell'oggetto TableAbsorber per trovare le tabelle
Successivamente, creeremo un oggetto TableAbsorber per trovare le tabelle nel documento PDF:

```csharp
// Crea un oggetto TableAbsorber per trovare le tabelle
TableAbsorber absorber = new TableAbsorber();
```

## Passaggio 3: visita la seconda pagina con l'assorbitore
Visiteremo ora la seconda pagina del documento PDF utilizzando l'assorbitore:

```csharp
// Visita la seconda pagina con l'assorbitore
absorb.Visit(pdfDocument.Pages[1]);
```

## Passaggio 4: ottenere una copia della collezione di tavoli
Per poter eliminare le tabelle, dobbiamo ottenere una copia della raccolta di tabelle:

```csharp
// Ottieni una copia della collezione di tavoli
AbsorbedTable[] tables = new AbsorbedTable[absorb.TableList.Count];
absorb.TableList.CopyTo(tables, 0);
```

## Passaggio 5: sfoglia la copia della raccolta e rimuovi le tabelle
Ora iteriamo attraverso la copia della raccolta di tabelle e rimuoviamole una per una:

```csharp
// Sfoglia la copia della raccolta e rimuovi le tabelle
foreach(AbsorbedTable table in tables)
     absorb.Remove(table);
```

## Passaggio 6: salvare il documento
Infine, salviamo il documento PDF modificato:

```csharp
// Salva il documento
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

### Codice sorgente di esempio per rimuovere più tabelle utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica il documento PDF esistente
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

// Crea un oggetto TableAbsorber per trovare le tabelle
TableAbsorber absorber = new TableAbsorber();

// Visita la seconda pagina con assorbitore
absorber.Visit(pdfDocument.Pages[1]);

// Ottieni una copia della collezione di tavoli
AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
absorber.TableList.CopyTo(tables, 0);

// Eseguire il ciclo della copia della raccolta e rimuovere le tabelle
foreach (AbsorbedTable table in tables)
	absorber.Remove(table);

// Salva documento
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

## Conclusione
Congratulazioni! Ora hai imparato come rimuovere più tabelle in un documento PDF utilizzando Aspose.PDF per .NET. Questa guida dettagliata ti ha mostrato come caricare il documento, trovare le tabelle e rimuoverle. Ora puoi applicare questa conoscenza ai tuoi progetti.