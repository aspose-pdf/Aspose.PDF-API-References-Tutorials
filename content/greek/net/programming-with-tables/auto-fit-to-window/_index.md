---
title: Αυτόματη προσαρμογή στο παράθυρο
linktitle: Αυτόματη προσαρμογή στο παράθυρο
second_title: Aspose.PDF για Αναφορά API .NET
description: Οδηγός βήμα προς βήμα για τη χρήση του Aspose.PDF για .NET και την επίτευξη αυτόματης προσαρμογής στο παράθυρο στη δημιουργία PDF.
type: docs
weight: 50
url: /el/net/programming-with-tables/auto-fit-to-window/
---
Το παρακάτω άρθρο είναι ένας αναλυτικός οδηγός σχετικά με τον τρόπο χρήσης του παρεχόμενου πηγαίου κώδικα C# για την επίτευξη της λειτουργίας Auto Fit To Window χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Η λειτουργία Auto Fit To Window σάς επιτρέπει να δημιουργείτε αρχεία PDF με διάταξη προσαρμοσμένη στο παράθυρο προβολής. Αυτή η δυνατότητα είναι ιδιαίτερα χρήσιμη όταν θέλετε το έγγραφο PDF σας να προσαρμόζεται αυτόματα στο μέγεθος του παραθύρου του προγράμματος ανάγνωσης PDF που χρησιμοποιείται από τον χρήστη.

## Βήμα 1: Ρύθμιση του περιβάλλοντος

Πριν ξεκινήσετε, πρέπει να εγκαταστήσετε τη βιβλιοθήκη Aspose.PDF για .NET στον υπολογιστή σας. Φροντίστε επίσης να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργία εγγράφου PDF

 Για να ξεκινήσετε, πρέπει να δημιουργήσετε ένα`Document` αντικείμενο καλώντας τον προεπιλεγμένο κατασκευαστή του.

```csharp
Document doc = new Document();
```

 Στη συνέχεια, δημιουργήστε μια ενότητα στο`Pdf` αντικείμενο.

```csharp
Page sec1 = doc.Pages.Add();
```

## Βήμα 3: Προσθήκη πίνακα στο έγγραφο

 Σε αυτό το βήμα, θα προσθέσουμε έναν πίνακα στο έγγραφο PDF μας. Πρώτα δημιουργήστε ένα`Table` αντικείμενο.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Στη συνέχεια, προσθέστε τον πίνακα στη συλλογή παραγράφων της ενότητας.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Βήμα 4: Προσαρμογή της εμφάνισης του πίνακα

Μπορείτε να προσαρμόσετε την εμφάνιση του πίνακα ορίζοντας ιδιότητες όπως περιθώρια κελιών και περιθώριο.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Βήμα 4: Προσθήκη γραμμών και κελιών στον πίνακα

Τώρα ας προσθέσουμε γραμμές και κελιά στον πίνακά μας. Ξεκινήστε δημιουργώντας μια σειρά και προσθέτοντας κελιά σε αυτήν τη σειρά.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Βήμα 5: Αποθήκευση του εγγράφου

Τέλος, καθορίστε τη διαδρομή του αρχείου εξόδου και αποθηκεύστε το έγγραφο.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Παράδειγμα πηγαίου κώδικα για την αυτόματη προσαρμογή σε παράθυρο χρησιμοποιώντας το Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργήστε το αντικείμενο Pdf καλώντας τον κενό κατασκευαστή του
Document doc = new Document();
// Δημιουργήστε την ενότητα στο αντικείμενο Pdf
Page sec1 = doc.Pages.Add();

// Δημιουργήστε ένα αντικείμενο πίνακα
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Προσθέστε τον πίνακα στη συλλογή παραγράφων της επιθυμητής ενότητας
sec1.Paragraphs.Add(tab1);

// Σετ με τα πλάτη στηλών του πίνακα
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Ορίστε το προεπιλεγμένο περίγραμμα κελιού χρησιμοποιώντας το αντικείμενο BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Ορισμός περιγράμματος πίνακα χρησιμοποιώντας ένα άλλο προσαρμοσμένο αντικείμενο BorderInfo
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Δημιουργήστε αντικείμενο MarginInfo και ορίστε τα περιθώρια αριστερά, κάτω, δεξιά και πάνω
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Ορίστε την προεπιλεγμένη συμπλήρωση κελιών στο αντικείμενο MarginInfo
tab1.DefaultCellPadding = margin;

// Δημιουργήστε σειρές στον πίνακα και μετά κελιά στις σειρές
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Αποθηκεύστε το ενημερωμένο έγγραφο που περιέχει αντικείμενο πίνακα
doc.Save(dataDir);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να χρησιμοποιούμε το Aspose.PDF για .NET για να δημιουργήσουμε ένα αρχείο PDF με τη δυνατότητα Auto Fit To Window. Αυτή η δυνατότητα είναι εξαιρετικά χρήσιμη όταν θέλετε το έγγραφο PDF σας να προσαρμόζεται αυτόματα στο μέγεθος του παραθύρου προβολής. Το Aspose.PDF για .NET προσφέρει πολλές άλλες ισχυρές δυνατότητες για τη δημιουργία και το χειρισμό αρχείων PDF. Σας ενθαρρύνω να εξερευνήσετε περαιτέρω αυτή τη βιβλιοθήκη για να ανακαλύψετε όλες τις δυνατότητές της.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός της δυνατότητας Auto Fit To Window στη δημιουργία PDF;

Α: Η λειτουργία Auto Fit To Window στη δημιουργία PDF διασφαλίζει ότι η διάταξη του εγγράφου PDF προσαρμόζεται αυτόματα στο μέγεθος του παραθύρου του προγράμματος ανάγνωσης PDF που χρησιμοποιείται από τον χρήστη. Αυτό επιτρέπει την καλύτερη προβολή και διασφαλίζει ότι το περιεχόμενο ταιριάζει απόλυτα στη διαθέσιμη περιοχή προβολής.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση του πίνακα, όπως το μέγεθος γραμματοσειράς και τα χρώματα;

Α: Ναι, μπορείτε να προσαρμόσετε την εμφάνιση του πίνακα στο έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Το παρεχόμενο απόσπασμα κώδικα δείχνει πώς να ορίσετε ιδιότητες όπως περιθώρια κελιών, περιθώρια και πλάτη στηλών. Μπορείτε να προσαρμόσετε περαιτέρω το μέγεθος της γραμματοσειράς, τα χρώματα και άλλες πτυχές του στυλ του πίνακα και του περιεχομένου του.

#### Ε: Πώς μπορώ να ενσωματώσω το Aspose.PDF για .NET στο έργο μου C#;

Α: Για να χρησιμοποιήσετε το Aspose.PDF για .NET στο έργο C#, πρέπει πρώτα να εγκαταστήσετε τη βιβλιοθήκη Aspose.PDF για .NET στον υπολογιστή σας. Στη συνέχεια, μπορείτε να προσθέσετε μια αναφορά στη βιβλιοθήκη στο έργο σας C#. Τέλος, εισαγάγετε τους απαραίτητους χώρους ονομάτων για πρόσβαση στις κλάσεις και τις μεθόδους που παρέχονται από το Aspose.PDF για .NET.

#### Ε: Είναι το Aspose.PDF για .NET συμβατό με εφαρμογές .NET Core;

Α: Ναι, το Aspose.PDF για .NET είναι συμβατό με εφαρμογές .NET Core. Υποστηρίζει διάφορες πλατφόρμες .NET, συμπεριλαμβανομένων των .NET Framework, .NET Core και .NET 5.0+.

#### Ε: Μπορώ να προσθέσω περισσότερους πίνακες στο έγγραφο PDF;

Α: Ναι, μπορείτε να προσθέσετε πολλούς πίνακες σε ένα έγγραφο PDF ακολουθώντας παρόμοια βήματα όπως φαίνεται στο απόσπασμα κώδικα. Απλώς δημιουργήστε νέες περιπτώσεις του`Aspose.Pdf.Table` τάξη και προσθέστε τα σε διαφορετικές ενότητες ή σελίδες του εγγράφου PDF.