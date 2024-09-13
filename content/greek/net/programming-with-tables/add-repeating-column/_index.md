---
title: Προσθήκη επαναλαμβανόμενης στήλης σε έγγραφο PDF
linktitle: Προσθήκη επαναλαμβανόμενης στήλης σε έγγραφο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς μπορείτε να προσθέσετε μια επαναλαμβανόμενη στήλη σε έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 20
url: /el/net/programming-with-tables/add-repeating-column/
---
Σε αυτό το σεμινάριο, θα μάθουμε πώς να προσθέτουμε μια επαναλαμβανόμενη στήλη σε έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα σε C# βήμα προς βήμα. Στο τέλος αυτού του σεμιναρίου, θα ξέρετε πώς να δημιουργήσετε έναν πίνακα με μια επαναλαμβανόμενη στήλη σε ένα έγγραφο PDF. Ας ξεκινήσουμε!

## Βήμα 1: Ρύθμιση περιβάλλοντος
Πρώτα, βεβαιωθείτε ότι έχετε ρυθμίσει το περιβάλλον ανάπτυξης C# με το Aspose.PDF για .NET. Προσθέστε την αναφορά στη βιβλιοθήκη και εισαγάγετε τους απαραίτητους χώρους ονομάτων.

## Βήμα 2: Δημιουργία του εγγράφου PDF
Σε αυτό το βήμα, δημιουργούμε ένα νέο έγγραφο PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Έχουμε δημιουργήσει ένα κενό έγγραφο PDF όπου μπορούμε να προσθέσουμε περιεχόμενο.

## Βήμα 3: Δημιουργία πινάκων
Σε αυτό το βήμα δημιουργούμε έναν κεντρικό πίνακα (`outerTable`) και ένα ένθετο τραπέζι (`mytable`) που θα επαναληφθεί στη στήλη.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Καθορίσαμε ιδιότητες πίνακα, όπως το πλάτος της στήλης και τη λειτουργία ένθεσης αλλαγής πίνακα.

## Βήμα 4: Προσθήκη των πινάκων στο έγγραφο
Τώρα προσθέτουμε τους πίνακες που δημιουργήσαμε στο έγγραφο PDF.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Προσθέτουμε πρώτα τον κύριο πίνακα (`outerTable`) στο έγγραφο PDF. Στη συνέχεια, προσθέτουμε τον ένθετο πίνακα (`mytable` ) ως παράγραφο σε ένα κελί στον κύριο πίνακα. Καθορίζουμε επίσης τον αριθμό των επαναλαμβανόμενων στηλών για`mytable` (σε αυτό το παράδειγμα, 5 στήλες).

## Βήμα 5: Προσθήκη κεφαλίδων και γραμμών
Τώρα προσθέτουμε τις κεφαλίδες και τις σειρές στον πίνακα.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
//Προσθέστε άλλες κεφαλίδες εδώ

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Προσθέστε τις άλλες στήλες εδώ
}
```

Προσθέτουμε πρώτα τις κεφαλίδες στην πρώτη σειρά του πίνακα (`headerRow`). Στη συνέχεια προσθέτουμε τις σειρές δεδομένων από έναν βρόχο. Σε αυτό το παράδειγμα, προσθέτουμε 6 σειρές δεδομένων.

## Βήμα 6: Αποθήκευση του εγγράφου PDF
Τέλος, αποθηκεύουμε το έγγραφο PDF στο καθορισμένο αρχείο.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Βεβαιωθείτε ότι έχετε καθορίσει τον σωστό κατάλογο και όνομα αρχείου για να αποθηκεύσετε το αρχείο PDF εξόδου.

### Παράδειγμα πηγαίου κώδικα για προσθήκη επαναλαμβανόμενης στήλης χρησιμοποιώντας το Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Δημιουργήστε ένα νέο έγγραφο
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Δημιουργήστε έναν εξωτερικό πίνακα που καταλαμβάνει ολόκληρη τη σελίδα
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

// Δημιουργήστε ένα αντικείμενο πίνακα που θα είναι ένθετο μέσα στο outerTable που θα σπάσει μέσα στην ίδια σελίδα
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Προσθέστε τον εξωτερικό Πίνακα στις παραγράφους της σελίδας
// Προσθήκη mytable στο outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Προσθήκη σειράς κεφαλίδας
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Δημιουργήστε σειρές στον πίνακα και μετά κελιά στις σειρές
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Σύναψη
Σε αυτό το σεμινάριο, μάθαμε πώς να προσθέτουμε μια επαναλαμβανόμενη στήλη σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε να χρησιμοποιήσετε αυτόν τον οδηγό βήμα προς βήμα για να δημιουργήσετε πίνακες με επαναλαμβανόμενες στήλες στα δικά σας έργα C#.

### Συχνές ερωτήσεις για την προσθήκη επαναλαμβανόμενης στήλης σε έγγραφο PDF

#### Ε: Μπορώ να προσαρμόσω τον αριθμό των επαναλαμβανόμενων στηλών στον ένθετο πίνακα;

 Α: Ναι, μπορείτε να προσαρμόσετε τον αριθμό των επαναλαμβανόμενων στηλών στον ένθετο πίνακα. Στο παρεχόμενο παράδειγμα, ορίσαμε`mytable.RepeatingColumnsCount = 5;`, που σημαίνει ότι θα υπάρχουν 5 επαναλαμβανόμενες στήλες. Μπορείτε να αλλάξετε αυτήν την τιμή σε οποιονδήποτε επιθυμητό αριθμό.

#### Ε: Είναι δυνατή η δυναμική προσθήκη περισσότερων σειρών στον ένθετο πίνακα;

Α: Ναι, μπορείτε να προσθέσετε δυναμικά περισσότερες σειρές στον ένθετο πίνακα με τον ίδιο τρόπο όπως φαίνεται στο σεμινάριο. Μπορείτε να χρησιμοποιήσετε βρόχους ή οποιαδήποτε άλλη λογική για να προσθέσετε σειρές με βάση τα δεδομένα σας.

#### Ε: Μπορώ να εφαρμόσω στυλ και μορφοποίηση στον πίνακα και τα κελιά του;

Α: Ναι, μπορείτε να εφαρμόσετε στυλ και μορφοποίηση στον πίνακα και τα κελιά του χρησιμοποιώντας το Aspose.PDF για .NET. Η βιβλιοθήκη παρέχει διάφορες ιδιότητες και μεθόδους για την προσαρμογή της εμφάνισης του πίνακα και των περιεχομένων του.

#### Ε: Είναι το Aspose.PDF για .NET συμβατό με .NET Core;

Α: Ναι, το Aspose.PDF για .NET είναι συμβατό με .NET Core. Μπορείτε να το χρησιμοποιήσετε τόσο σε εφαρμογές .NET Framework όσο και σε εφαρμογές .NET Core.

#### Ε: Μπορώ να χρησιμοποιήσω αυτήν την προσέγγιση για να προσθέσω επαναλαμβανόμενες στήλες σε ένα υπάρχον έγγραφο PDF;

Α: Ναι, μπορείτε να χρησιμοποιήσετε αυτήν την προσέγγιση για να προσθέσετε επαναλαμβανόμενες στήλες σε ένα υπάρχον έγγραφο PDF. Απλώς φορτώστε το υπάρχον έγγραφο χρησιμοποιώντας το Aspose.PDF για .NET και ακολουθήστε τα ίδια βήματα για να δημιουργήσετε και να προσθέσετε την επαναλαμβανόμενη στήλη.