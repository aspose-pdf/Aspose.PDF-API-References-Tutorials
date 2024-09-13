---
title: Περιθώρια ή Γέμισμα
linktitle: Περιθώρια ή Γέμισμα
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να ορίζετε περιθώρια ή συμπληρώσεις σε έναν πίνακα χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 140
url: /el/net/programming-with-tables/margins-or-padding/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα χρήσης του Aspose.PDF για .NET για να ορίσετε περιθώρια ή padding σε έναν πίνακα. Θα παρέχουμε επεξηγήσεις και αποσπάσματα κώδικα για να σας βοηθήσουμε να κατανοήσετε και να εφαρμόσετε αυτήν τη λειτουργία στον πηγαίο κώδικα C#.

## Βήμα 1: Ρύθμιση του Εγγράφου και της Σελίδας
Για να ξεκινήσετε, πρέπει να ρυθμίσετε το έγγραφο και τη σελίδα χρησιμοποιώντας τον ακόλουθο κώδικα:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργήστε το αντικείμενο Document καλώντας τον κενό κατασκευαστή του
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Βήμα 2: Δημιουργία πίνακα
Στη συνέχεια, θα δημιουργήσουμε ένα αντικείμενο πίνακα χρησιμοποιώντας την κλάση Aspose.Pdf.Table:

```csharp
// Δημιουργήστε ένα αντικείμενο πίνακα
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Προσθέστε τον πίνακα στη συλλογή παραγράφων της επιθυμητής ενότητας
page.Paragraphs.Add(tab1);
```

## Βήμα 3: Ρύθμιση πλάτη στηλών και προεπιλεγμένο περίγραμμα κελιού
Για να ορίσετε τα πλάτη στηλών και το προεπιλεγμένο περίγραμμα κελιών του πίνακα, χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
// Ορίστε τα πλάτη στηλών του πίνακα
tab1. ColumnWidths = "50 50 50";
// Ορίστε το προεπιλεγμένο περίγραμμα κελιού χρησιμοποιώντας το αντικείμενο BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Βήμα 4: Ρύθμιση περιγράμματος πίνακα και πλήρωσης κελιών
Για να ορίσετε το περίγραμμα του πίνακα και την πλήρωση κελιών, δημιουργήστε ένα αντικείμενο MarginInfo και ορίστε τις ιδιότητές του:

```csharp
// Δημιουργήστε ένα αντικείμενο MarginInfo και ορίστε τα αριστερά, κάτω, δεξιά και επάνω περιθώρια
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Ορίστε την προεπιλεγμένη συμπλήρωση κελιών στο αντικείμενο MarginInfo
tab1. DefaultCellPadding = margin;

// Ορίστε το περίγραμμα του πίνακα χρησιμοποιώντας ένα άλλο προσαρμοσμένο αντικείμενο BorderInfo
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Βήμα 5: Προσθήκη σειρών και κελιών
Τώρα, ας προσθέσουμε γραμμές και κελιά στον πίνακα. Θα δημιουργήσουμε μια νέα σειρά και θα προσθέσουμε κελιά σε αυτήν:

```csharp
//Δημιουργήστε σειρές στον πίνακα και μετά κελιά στις σειρές
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Βήμα 6: Προσθήκη κειμένου σε κελιά
Για να προσθέσετε κείμενο σε ένα κελί, δημιουργήστε ένα αντικείμενο TextFragment και προσθέστε το στο επιθυμητό κελί:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Βήμα 7: Αποθήκευση του PDF
Για να αποθηκεύσετε το έγγραφο PDF, χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Αποθηκεύστε το PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Παράδειγμα πηγαίου κώδικα για Margins or Padding χρησιμοποιώντας Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργήστε το αντικείμενο Document καλώντας τον κενό κατασκευαστή του
Document doc = new Document();
Page page = doc.Pages.Add();
// Δημιουργήστε ένα αντικείμενο πίνακα
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Προσθέστε τον πίνακα στη συλλογή παραγράφων της επιθυμητής ενότητας
page.Paragraphs.Add(tab1);
// Σετ με τα πλάτη στηλών του πίνακα
tab1.ColumnWidths = "50 50 50";
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
//Δημιουργήστε σειρές στον πίνακα και μετά κελιά στις σειρές
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 με μεγάλη συμβολοσειρά κειμένου που θα τοποθετηθεί μέσα στο κελί");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Αποθηκεύστε το Pdf
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Σύναψη
Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να ορίζετε περιθώρια ή συμπλήρωση σε έναν πίνακα χρησιμοποιώντας το Aspose.PDF για .NET. Αυτή η γνώση θα σας βοηθήσει να βελτιώσετε τις δυνατότητες μορφοποίησης των εγγράφων σας και να κάνετε τους πίνακές σας οπτικά ελκυστικούς.

### Συχνές ερωτήσεις

#### Ε: Μπορώ να ορίσω διαφορετικά περιθώρια ή γέμιση για μεμονωμένα κελιά σε έναν πίνακα;

 Α: Ναι, μπορείτε να ορίσετε διαφορετικά περιθώρια ή padding για μεμονωμένα κελιά σε έναν πίνακα χρησιμοποιώντας το Aspose.PDF για .NET. Στο παρεχόμενο παράδειγμα, ορίσαμε την προεπιλεγμένη συμπλήρωση κελιών για ολόκληρο τον πίνακα χρησιμοποιώντας το`DefaultCellPadding` ιδιοκτησία. Για να ορίσετε διαφορετική συμπλήρωση για συγκεκριμένα κελιά, μπορείτε να αποκτήσετε πρόσβαση στο`MarginInfo` κάθε κελιού ξεχωριστά και να τροποποιήσετε τα περιθώριά τους.

#### Ε: Πώς μπορώ να αλλάξω το χρώμα ή το στυλ του περιγράμματος του πίνακα;

 Α: Για να αλλάξετε το χρώμα περιγράμματος ή το στυλ του πίνακα, μπορείτε να τροποποιήσετε το`Color` και`Width` ιδιότητες του`BorderInfo` αντικείμενο. Στο συγκεκριμένο παράδειγμα, ορίσαμε το χρώμα του περιγράμματος σε μαύρο και πλάτος 1F (ένα σημείο) χρησιμοποιώντας`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Μπορείτε να προσαρμόσετε το χρώμα και το πλάτος σύμφωνα με τις απαιτήσεις σας.

#### Ε: Είναι δυνατή η προσθήκη κεφαλίδων ή υποσέλιδων στον πίνακα;

Α: Ναι, μπορείτε να προσθέσετε κεφαλίδες ή υποσέλιδα στον πίνακα χρησιμοποιώντας το Aspose.PDF για .NET. Οι κεφαλίδες και τα υποσέλιδα είναι συνήθως ξεχωριστές σειρές που περιέχουν πρόσθετες πληροφορίες, όπως ετικέτες στηλών, τίτλους πινάκων ή δεδομένα σύνοψης. Μπορείτε να δημιουργήσετε επιπλέον σειρές, να τις προσθέσετε με διαφορετικό στυλ και να τις προσθέσετε πάνω ή κάτω από το περιεχόμενο του πίνακα.

#### Ε: Πώς μπορώ να προσαρμόσω τη στοίχιση κειμένου σε ένα κελί πίνακα;

 Α: Για να προσαρμόσετε τη στοίχιση κειμένου σε ένα κελί πίνακα, μπορείτε να χρησιμοποιήσετε το`HorizontalAlignment` και`VerticalAlignment` ιδιότητες του`TextFragment` αντικείμενο. Για παράδειγμα, για να στοιχίσετε το κείμενο οριζόντια στο κέντρο, μπορείτε να ορίσετε`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . Ομοίως, μπορείτε να ορίσετε`mytext.VerticalAlignment` για τον έλεγχο της κατακόρυφης ευθυγράμμισης.

#### Ε: Μπορώ να προσθέσω εικόνες στα κελιά του πίνακα αντί για κείμενο;

 Α: Ναι, μπορείτε να προσθέσετε εικόνες στα κελιά του πίνακα χρησιμοποιώντας το Aspose.PDF για .NET. Αντί να δημιουργήσετε ένα`TextFragment` αντικείμενο, μπορείτε να δημιουργήσετε ένα`Image` αντικείμενο, φορτώστε το αρχείο εικόνας και προσθέστε το στο επιθυμητό κελί χρησιμοποιώντας το`cell.Paragraphs.Add(image);`μέθοδος. Αυτό σας επιτρέπει να εισάγετε εικόνες στον πίνακα μαζί με περιεχόμενο κειμένου.