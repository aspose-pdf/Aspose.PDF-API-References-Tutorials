---
title: Integra con il database
linktitle: Integra con il database
second_title: Aspose.PDF per riferimento API .NET
description: Incorpora i dati da un database in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-tables/integrate-with-database/
---

In questo tutorial impareremo come incorporare i dati da un database in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente in C# passo dopo passo. Alla fine di questo tutorial, saprai come importare i dati della tabella da un database in un documento PDF. Iniziamo!

## Passaggio 1: configurazione dell'ambiente
Assicurati di aver configurato il tuo ambiente di sviluppo C# con Aspose.PDF per .NET. Aggiungere il riferimento alla libreria e importare gli spazi dei nomi necessari.

## Passaggio 2: creazione del DataTable
Creiamo un'istanza di DataTable per rappresentare i dati che vogliamo incorporare nel documento PDF. In questo esempio creiamo un DataTable con tre colonne: Employee_ID, Employee_Name e Gender. Aggiungiamo anche due righe alla DataTable con dati fittizi.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Passaggio 3: creazione del documento PDF e della tabella
Creiamo un'istanza di Document e aggiungiamo una pagina a questo documento. Successivamente, creiamo un'istanza Table per rappresentare la nostra tabella nel documento PDF. Definiamo le larghezze delle colonne della tabella e gli stili dei bordi.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Passaggio 4: importazione dei dati dal DataTable nella tabella
Usiamo il metodo ImportDataTable per importare i dati dal DataTable nella tabella nel documento PDF.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Passaggio 5: aggiunta della tabella al documento
Aggiungiamo la tabella alla raccolta dei paragrafi della pagina del documento.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Passaggio 6: salvare il documento
Salviamo il documento PDF con i dati dal database incorporato.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Congratulazioni! Ora sai come incorporare i dati del database in un documento PDF utilizzando Aspose.PDF per .NET.

### Codice sorgente di esempio per l'integrazione con il database utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//Aggiungere 2 righe nell'oggetto DataTable a livello di codice
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Crea un'istanza di documento
Document doc = new Document();
doc.Pages.Add();
// Inizializza una nuova istanza di Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Imposta la larghezza delle colonne della tabella
table.ColumnWidths = "40 100 100 100";
// Imposta il colore del bordo della tabella come LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Imposta il bordo per le celle della tabella
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Aggiungi oggetto tabella alla prima pagina del documento di input
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Salva il documento aggiornato contenente l'oggetto tabella
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Conclusione
In questo tutorial, abbiamo imparato come incorporare i dati da un database in un documento PDF utilizzando Aspose.PDF per .NET. Puoi utilizzare questa guida dettagliata per importare i dati dal tuo database e visualizzarli in documenti PDF. Esplora ulteriormente la documentazione di Aspose.PDF per scoprire altre funzionalità e possibilità offerte da questa potente libreria.