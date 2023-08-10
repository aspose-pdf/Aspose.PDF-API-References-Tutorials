---
title: Integra con il database nel file PDF
linktitle: Integra con il database nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Incorporare i dati da un database in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-tables/integrate-with-database/
---
In questo tutorial impareremo come incorporare i dati da un database in un file PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente in C# passo dopo passo. Alla fine di questo tutorial, saprai come importare i dati della tabella da un database in un documento PDF. Iniziamo!

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

### Esempio di codice sorgente per l'integrazione con il database utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Aggiungere 2 righe nell'oggetto DataTable a livello di codice
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

### Domande frequenti per l'integrazione con il database nel file PDF

#### D: Posso utilizzare Aspose.PDF per .NET con diversi tipi di database come MySQL, SQL Server o Oracle?

R: Sì, puoi utilizzare Aspose.PDF per .NET con diversi tipi di database come MySQL, SQL Server, Oracle e altri. Aspose.PDF per .NET fornisce funzionalità per leggere i dati da varie fonti di dati, inclusi database, file XML e altro. È possibile recuperare i dati dal tipo di database desiderato e inserirli in un DataTable o in qualsiasi altra struttura di dati compatibile con Aspose.PDF per .NET.

#### D: Come posso personalizzare l'aspetto della tabella nel documento PDF?

R: È possibile personalizzare l'aspetto della tabella nel documento PDF utilizzando varie proprietà fornite dalla libreria Aspose.PDF per .NET. Ad esempio, puoi impostare diversi stili di bordo, colori di sfondo, stili di carattere e allineamento per la tabella e le relative celle. Fare riferimento alla documentazione di Aspose.PDF per .NET per ulteriori dettagli sulla personalizzazione dell'aspetto della tabella.

#### D: È possibile aggiungere collegamenti ipertestuali o elementi interattivi ai dati importati dal database?

R: Sì, puoi aggiungere collegamenti ipertestuali o altri elementi interattivi ai dati importati dal database. Aspose.PDF per .NET supporta l'aggiunta di collegamenti ipertestuali, segnalibri e altri elementi interattivi al documento PDF. È possibile modificare il contenuto nel DataTable prima di importarlo nella tabella e includere collegamenti ipertestuali o altre funzionalità interattive.

#### D: Posso impaginare la tabella se supera un certo numero di righe?

 R: Sì, puoi impaginare la tabella se supera un certo numero di righe. Per raggiungere questo obiettivo, puoi utilizzare il`IsInNewPage`proprietà dell'oggetto Row per indicare che una nuova pagina dovrebbe iniziare dopo una riga specifica. È possibile calcolare il numero di righe da visualizzare per pagina e impostare il`IsInNewPage` proprietà di conseguenza.

#### D: Come posso esportare il documento PDF con i dati del database incorporato in diversi formati di file come DOCX o XLSX?

R: Aspose.PDF per .NET consente di convertire documenti PDF in vari altri formati di file, tra cui DOCX (Microsoft Word) e XLSX (Microsoft Excel). È possibile utilizzare la libreria Aspose.PDF per .NET in combinazione con altre librerie Aspose come Aspose.Words e Aspose.Cells per raggiungere questo obiettivo. Innanzitutto, salva il documento PDF con i dati del database incorporati, quindi utilizza la rispettiva libreria Aspose per convertirlo nel formato di file desiderato.