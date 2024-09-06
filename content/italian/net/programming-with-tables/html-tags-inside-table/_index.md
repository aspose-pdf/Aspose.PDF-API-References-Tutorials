---
title: Tag HTML all'interno della tabella nel file PDF
linktitle: Tag HTML all'interno della tabella nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come utilizzare i tag HTML all'interno di una tabella in un file PDF con Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-tables/html-tags-inside-table/
---
In questo tutorial, impareremo come usare i tag HTML all'interno di una tabella in un documento PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente in C# passo dopo passo. Alla fine di questo tutorial, saprai come inserire contenuto HTML in una tabella in un documento PDF. Cominciamo!

## Fase 1: Impostazione dell'ambiente
Assicurati di aver configurato il tuo ambiente di sviluppo C# con Aspose.PDF per .NET. Aggiungi il riferimento alla libreria e importa i namespace necessari.

## Passaggio 2: creazione dei dati della tabella
Creiamo una DataTable contenente una colonna "data" di tipo String. Aggiungiamo quindi righe a questa DataTable utilizzando contenuto HTML.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Fase 3: Creazione del documento e della tabella
Creiamo un nuovo documento PDF e aggiungiamo una pagina in questo documento. Poi, inizializziamo un'istanza della classe Table e impostiamo le proprietà della tabella.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Fase 4: Importazione dei dati nella tabella
Importiamo i dati dalla DataTable nella tabella usando il metodo "ImportDataTable". Specifichiamo i parametri del metodo per indicare quale intervallo di righe e colonne della DataTable deve essere importato.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Passaggio 5: aggiunta della tabella al documento
Aggiungiamo la tabella alla pagina del documento.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Fase 6: Salvataggio del documento
Salviamo il documento PDF con la tabella contenente il contenuto HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Esempio di codice sorgente per tag HTML all'interno della tabella utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Inizializza una nuova istanza della tabella
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Imposta la larghezza delle colonne della tabella
tableProvider.ColumnWidths = "400 50 ";
// Imposta il colore del bordo della tabella come LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Imposta il bordo per le celle della tabella
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come usare i tag HTML all'interno di una tabella in un documento PDF usando Aspose.PDF per .NET. Puoi usare questa guida passo passo per inserire contenuto HTML nelle celle di tabella in un documento PDF usando C#.

### Domande frequenti sui tag HTML all'interno della tabella nel file PDF

#### D: Posso utilizzare altri tag e attributi HTML all'interno delle celle della tabella?

 A: Sì, puoi utilizzare vari tag e attributi HTML all'interno delle celle della tabella, come ad esempio`<b>`, `<i>`, `<a>`molti altri. Aspose.PDF per .NET supporta un'ampia gamma di elementi e stili HTML che puoi usare per formattare il contenuto all'interno delle celle della tabella.

#### D: Posso applicare stili CSS al contenuto HTML all'interno delle celle della tabella?

R: Sì, puoi applicare stili CSS al contenuto HTML all'interno delle celle della tabella. Aspose.PDF per .NET fornisce supporto per stili CSS di base che possono essere applicati agli elementi HTML.

#### D: È possibile aggiungere immagini insieme al contenuto HTML all'interno delle celle della tabella?

 A: Sì, puoi aggiungere immagini insieme al contenuto HTML all'interno delle celle della tabella. Puoi usare HTML`<img>` tag per includere immagini da varie fonti, come file locali o URL.

#### D: Come posso specificare diverse larghezze di colonna per la tabella?

 A: È possibile specificare diverse larghezze di colonna per la tabella utilizzando`ColumnWidths` proprietà della tabella. La proprietà accetta una stringa contenente valori separati da spazi, dove ogni valore rappresenta la larghezza di una colonna in punti.

#### D: Posso utilizzare tabelle nidificate all'interno di una cella con contenuto HTML?

R: Sì, puoi usare tabelle nidificate all'interno di una cella con contenuto HTML. Puoi creare istanze di tabella separate e aggiungerle come parte del contenuto HTML all'interno di una cella per ottenere l'effetto di nidificazione.