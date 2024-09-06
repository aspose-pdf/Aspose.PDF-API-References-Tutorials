---
title: Ετικέτες HTML μέσα στον πίνακα σε αρχείο PDF
linktitle: Ετικέτες HTML μέσα στον πίνακα σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να χρησιμοποιείτε ετικέτες HTML μέσα σε έναν πίνακα σε αρχείο PDF με το Aspose.PDF για .NET.
type: docs
weight: 100
url: /el/net/programming-with-tables/html-tags-inside-table/
---
Σε αυτό το σεμινάριο, θα μάθουμε πώς να χρησιμοποιούμε ετικέτες HTML μέσα σε έναν πίνακα σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα σε C# βήμα προς βήμα. Στο τέλος αυτού του σεμιναρίου, θα ξέρετε πώς να εισάγετε περιεχόμενο HTML σε έναν πίνακα σε ένα έγγραφο PDF. Ας ξεκινήσουμε!

## Βήμα 1: Ρύθμιση περιβάλλοντος
Βεβαιωθείτε ότι έχετε διαμορφώσει το περιβάλλον ανάπτυξης C# με το Aspose.PDF για .NET. Προσθέστε την αναφορά στη βιβλιοθήκη και εισαγάγετε τους απαραίτητους χώρους ονομάτων.

## Βήμα 2: Δημιουργία δεδομένων πίνακα
Δημιουργούμε ένα DataTable που περιέχει μια στήλη "data" τύπου String. Στη συνέχεια προσθέτουμε σειρές σε αυτόν τον πίνακα δεδομένων χρησιμοποιώντας περιεχόμενο HTML.

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

## Βήμα 3: Δημιουργία εγγράφου και πίνακα
Δημιουργούμε ένα νέο έγγραφο PDF και προσθέτουμε μια σελίδα σε αυτό το έγγραφο. Στη συνέχεια, αρχικοποιούμε μια παρουσία της κλάσης Table και ορίζουμε τις ιδιότητες του πίνακα.

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

## Βήμα 4: Εισαγωγή δεδομένων στον πίνακα
Εισάγουμε τα δεδομένα από τον πίνακα δεδομένων στον πίνακα χρησιμοποιώντας τη μέθοδο "ImportDataTable". Καθορίζουμε τις παραμέτρους της μεθόδου για να υποδείξουμε ποιο εύρος γραμμών και στηλών του DataTable πρέπει να εισαχθεί.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Βήμα 5: Προσθήκη του πίνακα στο έγγραφο
Προσθέτουμε τον πίνακα στη σελίδα του εγγράφου.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Στάδιο 6: Αποθήκευση του εγγράφου
Αποθηκεύουμε το έγγραφο PDF με τον πίνακα που περιέχει περιεχόμενο HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Παράδειγμα πηγαίου κώδικα για ετικέτες HTML μέσα στον πίνακα χρησιμοποιώντας το Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
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
// Αρχικοποιεί μια νέα παρουσία του πίνακα
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Ορίστε τα πλάτη στηλών του πίνακα
tableProvider.ColumnWidths = "400 50 ";
// Ορίστε το χρώμα περιγράμματος του πίνακα ως Ανοιχτό Γκρι
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Ορίστε το περίγραμμα για τα κελιά του πίνακα
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

## Σύναψη
Σε αυτό το σεμινάριο, μάθαμε πώς να χρησιμοποιούμε ετικέτες HTML μέσα σε έναν πίνακα σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε να χρησιμοποιήσετε αυτόν τον οδηγό βήμα προς βήμα για να εισαγάγετε περιεχόμενο HTML σε κελιά πίνακα σε ένα έγγραφο PDF χρησιμοποιώντας C#.

### Συχνές ερωτήσεις για ετικέτες HTML μέσα στον πίνακα σε αρχείο PDF

#### Ε: Μπορώ να χρησιμοποιήσω άλλες ετικέτες και χαρακτηριστικά HTML μέσα στα κελιά του πίνακα;

 Α: Ναι, μπορείτε να χρησιμοποιήσετε διάφορες ετικέτες και χαρακτηριστικά HTML μέσα στα κελιά του πίνακα, όπως π.χ`<b>`, `<i>`, `<a>`και πολλά άλλα. Το Aspose.PDF για .NET υποστηρίζει ένα ευρύ φάσμα στοιχείων HTML και στυλ που μπορείτε να χρησιμοποιήσετε για να μορφοποιήσετε το περιεχόμενο στα κελιά του πίνακα.

#### Ε: Μπορώ να εφαρμόσω στυλ CSS στο περιεχόμενο HTML μέσα στα κελιά του πίνακα;

Α: Ναι, μπορείτε να εφαρμόσετε στυλ CSS στο περιεχόμενο HTML μέσα στα κελιά του πίνακα. Το Aspose.PDF για .NET παρέχει υποστήριξη για βασικά στυλ CSS που μπορούν να εφαρμοστούν στα στοιχεία HTML.

#### Ε: Είναι δυνατή η προσθήκη εικόνων μαζί με περιεχόμενο HTML μέσα στα κελιά του πίνακα;

 Α: Ναι, μπορείτε να προσθέσετε εικόνες μαζί με περιεχόμενο HTML μέσα στα κελιά του πίνακα. Μπορείτε να χρησιμοποιήσετε HTML`<img>` ετικέτες για να περιλαμβάνουν εικόνες από διάφορες πηγές, όπως τοπικά αρχεία ή διευθύνσεις URL.

#### Ε: Πώς μπορώ να καθορίσω διαφορετικά πλάτη στηλών για τον πίνακα;

 Α: Μπορείτε να καθορίσετε διαφορετικά πλάτη στηλών για τον πίνακα χρησιμοποιώντας το`ColumnWidths` ιδιοκτησία του πίνακα. Η ιδιότητα παίρνει μια συμβολοσειρά που περιέχει τιμές διαχωρισμένες με διάστημα, όπου κάθε τιμή αντιπροσωπεύει το πλάτος μιας στήλης σε σημεία.

#### Ε: Μπορώ να χρησιμοποιήσω ένθετους πίνακες μέσα σε ένα κελί με περιεχόμενο HTML;

Α: Ναι, μπορείτε να χρησιμοποιήσετε ένθετους πίνακες μέσα σε ένα κελί με περιεχόμενο HTML. Μπορείτε να δημιουργήσετε ξεχωριστές παρουσίες πίνακα και να τις προσθέσετε ως μέρος του περιεχομένου HTML μέσα σε ένα κελί για να επιτύχετε το εφέ ένθεσης.