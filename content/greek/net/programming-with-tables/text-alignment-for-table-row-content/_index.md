---
title: Στοίχιση κειμένου για περιεχόμενο σειρών πίνακα
linktitle: Στοίχιση κειμένου για περιεχόμενο σειρών πίνακα
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να ευθυγραμμίζετε το περιεχόμενο σειρών σε έναν πίνακα PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 210
url: /el/net/programming-with-tables/text-alignment-for-table-row-content/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε βήμα προς βήμα για να ευθυγραμμίσετε τα περιεχόμενα μιας σειράς σε έναν πίνακα ενός εγγράφου PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα εξηγήσουμε τον παρεχόμενο πηγαίο κώδικα C# και θα σας δείξουμε πώς να τον εφαρμόσετε.

## Βήμα 1: Δημιουργία του εγγράφου PDF
Αρχικά, θα δημιουργήσουμε το έγγραφο PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Βήμα 2: Αρχικοποίηση πίνακα
Στη συνέχεια, θα αρχικοποιήσουμε τον πίνακα:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Βήμα 3: Ορισμός χρώματος περιγράμματος πίνακα
Θα διαμορφώσουμε το χρώμα του περιγράμματος του πίνακα:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Βήμα 4: Διαμόρφωση του περιγράμματος κελιών πίνακα
Θα διαμορφώσουμε το περίγραμμα κελιών του πίνακα:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Βήμα 5: Κάντε βρόχο για να προσθέσετε 10 σειρές στον πίνακα
Τώρα θα χρησιμοποιήσουμε έναν βρόχο για να προσθέσουμε 10 σειρές στον πίνακα:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Βήμα 6: Διαμόρφωση της ευθυγράμμισης κάθετης γραμμής
Θα διαμορφώσουμε την κατακόρυφη στοίχιση των σειρών του πίνακα:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Βήμα 7: Προσθήκη περιεχομένου σε κελιά σειράς
Θα προσθέσουμε περιεχόμενο στα κελιά της σειράς:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Βήμα 8: Προσθήκη του πίνακα στη σελίδα του εγγράφου
Τώρα ας προσθέσουμε τον πίνακα στη σελίδα του εγγράφου:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Βήμα 9: Αποθήκευση του εγγράφου PDF
Τέλος, θα αποθηκεύσουμε το έγγραφο PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Παράδειγμα πηγαίου κώδικα για στοίχιση κειμένου για περιεχόμενο σειρών πίνακα χρησιμοποιώντας το Aspose.PDF για .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργία εγγράφου PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Αρχικοποιεί μια νέα παρουσία του πίνακα
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ορίστε το χρώμα περιγράμματος του πίνακα ως Ανοιχτό Γκρι
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// ορίστε το περίγραμμα για τα κελιά του πίνακα
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// δημιουργήστε έναν βρόχο για να προσθέσετε 10 σειρές
for (int row_count = 0; row_count < 10; row_count++)
{
	// προσθήκη σειράς στον πίνακα
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Προσθήκη αντικειμένου πίνακα στην πρώτη σελίδα του εγγράφου εισαγωγής
tocPage.Paragraphs.Add(table);
// Αποθηκεύστε το ενημερωμένο έγγραφο που περιέχει αντικείμενο πίνακα
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## συμπέρασμα
Συγχαρητήρια ! Τώρα μάθατε πώς να στοιχίζετε τα περιεχόμενα μιας σειράς σε έναν πίνακα σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Αυτός ο οδηγός βήμα προς βήμα σάς έδειξε πώς να δημιουργήσετε ένα έγγραφο, να αρχικοποιήσετε έναν πίνακα, να διαμορφώσετε το περίγραμμα και τη στοίχιση, να προσθέσετε περιεχόμενο και να αποθηκεύσετε το έγγραφο PDF. Τώρα μπορείτε να εφαρμόσετε αυτή τη γνώση στα δικά σας έργα.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να ευθυγραμμίσω τα περιεχόμενα των κελιών του πίνακα οριζόντια;

 Α: Μπορείτε να ευθυγραμμίσετε τα περιεχόμενα των κελιών του πίνακα οριζόντια ορίζοντας το`HorizontalAlign` ιδιοκτησία του κυττάρου`TextState` αντικείμενο. Για παράδειγμα, για να στοιχίσετε το κείμενο στο κέντρο, χρησιμοποιήστε`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Μπορείτε επίσης να το ρυθμίσετε σε`HorizontalAlignment.Left` ή`HorizontalAlignment.Right` για ευθυγράμμιση αριστερά και δεξιά, αντίστοιχα.

#### Ε: Μπορώ να εφαρμόσω διαφορετικά στυλ περιγράμματος και χρώματα σε μεμονωμένα κελιά του πίνακα;

 Α: Ναι, μπορείτε να εφαρμόσετε διαφορετικά στυλ περιγράμματος και χρώματα σε μεμονωμένα κελιά του πίνακα. Για να προσαρμόσετε το περίγραμμα για ένα συγκεκριμένο κελί, ορίστε το`cell.Border` ακίνητο σε ένα νέο`BorderInfo`αντικείμενο με τις επιθυμητές ρυθμίσεις, όπως πλευρές περιγράμματος, πλάτος και χρώμα.

#### Ε: Πώς μπορώ να προσαρμόσω την κατακόρυφη στοίχιση του περιεχομένου του πίνακα μέσα στα κελιά;

 Α: Μπορείτε να προσαρμόσετε την κατακόρυφη στοίχιση του περιεχομένου του πίνακα εντός των κελιών ορίζοντας το`VerticalAlignment` ιδιοκτησία της σειράς προς`VerticalAlignment.Center`, `VerticalAlignment.Top` , ή`VerticalAlignment.Bottom`. Αυτή η ιδιότητα ελέγχει την κατακόρυφη στοίχιση όλων των κελιών σε αυτήν τη σειρά.

#### Ε: Είναι δυνατή η δυναμική προσθήκη περισσότερων στηλών ή γραμμών στον πίνακα;

 Α: Ναι, μπορείτε να προσθέσετε περισσότερες στήλες και σειρές στον πίνακα δυναμικά χρησιμοποιώντας το`table.Rows.Add()` μέθοδος προσθήκης νέων σειρών και το`row.Cells.Add()` μέθοδος προσθήκης νέων κελιών στις σειρές. Μπορείτε να το κάνετε αυτό μέσα σε βρόχους ή με βάση τις συγκεκριμένες απαιτήσεις σας.

#### Ε: Πώς μπορώ να ορίσω ένα χρώμα φόντου για συγκεκριμένα κελιά ή ολόκληρο τον πίνακα;

 Α: Για να ορίσετε ένα χρώμα φόντου για συγκεκριμένα κελιά ή ολόκληρο τον πίνακα, χρησιμοποιήστε το`BackgroundColor` ιδιοκτησία του`Cell` ή`Table` αντικείμενο. Για παράδειγμα, για να ορίσετε το χρώμα φόντου ενός κελιού, χρησιμοποιήστε το`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.