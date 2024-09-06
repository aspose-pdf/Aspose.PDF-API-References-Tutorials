---
title: Απόδοση πίνακα σε έγγραφο PDF
linktitle: Απόδοση πίνακα σε έγγραφο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να εμφανίζετε έναν πίνακα σε έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 170
url: /el/net/programming-with-tables/render-table/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε βήμα προς βήμα για να εμφανίσετε έναν πίνακα σε έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα εξηγήσουμε τον παρεχόμενο πηγαίο κώδικα C# και θα σας δείξουμε πώς να τον εφαρμόσετε.

## Βήμα 1: Δημιουργία του εγγράφου
Αρχικά, θα δημιουργήσουμε ένα νέο έγγραφο PDF:

```csharp
// Διαδρομή στον κατάλογο εγγράφων
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργήστε ένα νέο έγγραφο
Document doc = new Document();
```

## Βήμα 2: Διαμόρφωση περιθωρίων και προσανατολισμού σελίδας
Στη συνέχεια, θα διαμορφώσουμε τα περιθώρια της σελίδας και θα ορίσουμε τον προσανατολισμό σε οριζόντια λειτουργία:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Βήμα 3: Δημιουργία πίνακα και στηλών
Τώρα ας δημιουργήσουμε έναν πίνακα και ας ορίσουμε τα πλάτη των στηλών:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Βήμα 4: Προσθέστε γραμμές και κελιά στον πίνακα
Στη συνέχεια, θα προσθέσουμε γραμμές και κελιά στον πίνακα χρησιμοποιώντας έναν βρόχο:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Βήμα 5: Προσθήκη του πίνακα στη σελίδα
Τώρα ας προσθέσουμε τον πίνακα στη σελίδα του εγγράφου:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Βήμα 6: Εμφάνιση του πίνακα σε νέα σελίδα
Στη συνέχεια, θα δημιουργήσουμε έναν νέο πίνακα και θα ορίσουμε την ιδιότητα "IsInNewPage" σε "true" για να εμφανιστεί ο πίνακας σε μια νέα σελίδα:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Βήμα 7: Αποθήκευση PDF
Τέλος, αποθηκεύουμε το έγγραφο PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Παράδειγμα πηγαίου κώδικα για Render Table χρησιμοποιώντας Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Προστέθηκε σελίδα.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Θέλω να κρατήσω τον πίνακα 1 στην επόμενη σελίδα, παρακαλώ...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Σύναψη
Συγχαρητήρια ! Τώρα έχετε μάθει πώς να εμφανίζετε έναν πίνακα σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Αυτός ο οδηγός βήμα προς βήμα σάς έδειξε πώς να δημιουργήσετε ένα έγγραφο, να διαμορφώσετε τα περιθώρια και τον προσανατολισμό της σελίδας, να προσθέσετε έναν πίνακα και να εμφανίσετε έναν πίνακα σε μια νέα σελίδα. Τώρα μπορείτε να εφαρμόσετε αυτή τη γνώση στα δικά σας έργα.

### Συχνές ερωτήσεις για τον πίνακα απόδοσης σε έγγραφο PDF

#### Ε: Πώς μπορώ να τροποποιήσω την εμφάνιση του πίνακα, όπως αλλαγή χρωμάτων κελιών ή προσθήκη περιγραμμάτων;

Α: Για να τροποποιήσετε την εμφάνιση του πίνακα, μπορείτε να ορίσετε διάφορες ιδιότητες του`Aspose.Pdf.Table` και τα κύτταρα του. Για παράδειγμα, μπορείτε να ορίσετε το`BackgroundColor` ιδιότητα των κελιών να αλλάζουν το χρώμα φόντου τους. Μπορείτε επίσης να ρυθμίσετε το`Border` ιδιότητα του πίνακα ή των μεμονωμένων κελιών για προσθήκη περιγραμμάτων. Επιπλέον, μπορείτε να προσαρμόσετε τη γραμματοσειρά, το χρώμα του κειμένου και τη στοίχιση του περιεχομένου του πίνακα τροποποιώντας το`TextState` του`TextFragment` αντικείμενα που προστέθηκαν στα κελιά.

#### Ε: Μπορώ να προσθέσω κεφαλίδες ή υποσέλιδα στον πίνακα;

Α: Ναι, μπορείτε να προσθέσετε κεφαλίδες ή υποσέλιδα στον πίνακα δημιουργώντας πρόσθετες σειρές στην αρχή ή στο τέλος του πίνακα και ορίζοντας το κατάλληλο περιεχόμενο στα κελιά. Μπορείτε να προσαρμόσετε τις κεφαλίδες ή τα υποσέλιδα ανεξάρτητα από το υπόλοιπο περιεχόμενο του πίνακα προσθέτοντας διαφορετικά στυλ ή περιεχόμενο σε αυτές τις συγκεκριμένες σειρές.

#### Ε: Πώς μπορώ να ελέγξω τη θέση του πίνακα στη σελίδα;

 Α: Για να ελέγξετε τη θέση του πίνακα στη σελίδα, μπορείτε να προσαρμόσετε το`MarginInfo` του`PageInfo` αντικείμενο. Ο`MarginInfo`σας επιτρέπει να ορίσετε τα αριστερά, δεξιά, επάνω και κάτω περιθώρια της σελίδας, γεγονός που επηρεάζει τον διαθέσιμο χώρο για τον πίνακα. Μπορείτε επίσης να χρησιμοποιήσετε το`PositioningType` ιδιοκτησία του`Aspose.Pdf.Table` για να ελέγξετε την οριζόντια και κάθετη στοίχιση εντός της περιοχής περιεχομένου της σελίδας.

#### Ε: Μπορώ να εξαγάγω τον πίνακα σε διαφορετικές μορφές αρχείων, όπως Excel ή CSV;

Α: Το Aspose.PDF για .NET έχει σχεδιαστεί κυρίως για εργασία με έγγραφα PDF. Ενώ μπορεί να εξάγει το έγγραφο PDF ως εικόνα ή XPS, δεν υποστηρίζει απευθείας την εξαγωγή πινάκων σε μορφές όπως το Excel ή το CSV. Για να εξαγάγετε τα δεδομένα του πίνακα σε διαφορετικές μορφές αρχείων, ίσως χρειαστεί να χρησιμοποιήσετε πρόσθετες βιβλιοθήκες ή μεθόδους για να μετατρέψετε το περιεχόμενο PDF στην επιθυμητή μορφή.

#### Ε: Πώς μπορώ να προσθέσω υπερσυνδέσμους στα κελιά του πίνακα;

 Α: Για να προσθέσετε υπερσυνδέσμους στα κελιά του πίνακα, μπορείτε να χρησιμοποιήσετε το`Aspose.Pdf.WebHyperlink` τάξη για να δημιουργήσετε έναν υπερσύνδεσμο και στη συνέχεια να τον προσθέσετε ως άγκυρα στο`TextFragment`μέσα στο κελί. Αυτό σας επιτρέπει να συσχετίσετε μια διεύθυνση URL ή έναν στόχο συνδέσμου με συγκεκριμένο κείμενο ή περιεχόμενο εντός του κελιού, δημιουργώντας υπερσυνδέσμους με δυνατότητα κλικ.