---
title: Πίνακας στην ενότητα υποσέλιδου κεφαλίδας
linktitle: Πίνακας στην ενότητα υποσέλιδου κεφαλίδας
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς μπορείτε να προσθέσετε έναν πίνακα στην ενότητα κεφαλίδας/υποσέλιδου ενός εγγράφου PDF με το Aspose.PDF για .NET.
type: docs
weight: 170
url: /el/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε βήμα προς βήμα για το πώς να προσθέσετε έναν πίνακα στην ενότητα κεφαλίδας ή υποσέλιδου ενός εγγράφου PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# σάς δείχνει πώς να δημιουργήσετε ένα κενό έγγραφο PDF, να προσθέσετε μια σελίδα, να διαμορφώσετε την ενότητα κεφαλίδας, να δημιουργήσετε έναν πίνακα, να προσθέσετε σειρές και κελιά στον πίνακα και, τέλος, να αποθηκεύσετε το έγγραφο PDF.

## Βήμα 1: Ρύθμιση περιβάλλοντος

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Ένα εγκατεστημένο περιβάλλον ανάπτυξης .NET.
- Η βιβλιοθήκη Aspose.PDF για .NET έγινε λήψη και αναφορά στο έργο σας.

## Βήμα 2: Δημιουργία του εγγράφου και της σελίδας PDF

 Το πρώτο βήμα είναι να δημιουργήσετε ένα παράδειγμα του`Document` τάξη και προσθέστε μια σελίδα στο έγγραφο. Δείτε πώς:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργήστε ένα αντικείμενο εγγράφου
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Δημιουργήστε μια σελίδα στο έγγραφο PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Φροντίστε να αντικαταστήσετε το "YOUR DOCUMENTS DECTORY" με την πραγματική διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο PDF.

## Βήμα 3: Διαμόρφωση της ενότητας κεφαλίδας

 Τώρα θα διαμορφώσουμε την ενότητα κεφαλίδας του εγγράφου PDF δημιουργώντας μια παρουσία του`HeaderFooter` τάξη. Δείτε πώς:

```csharp
// Δημιουργήστε μια ενότητα κεφαλίδας για το αρχείο PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Καθορίστε την ενότητα κεφαλίδας για τη σελίδα
page. Header = header;

// Ορίστε το επάνω περιθώριο του τμήματος κεφαλίδας
header. Margin. Top = 20;
```

## Βήμα 4: Δημιουργία πίνακα

 Τώρα θα δημιουργήσουμε έναν πίνακα χρησιμοποιώντας το`Table` τάξη και προσθέστε το στη συλλογή παραγράφων της ενότητας επικεφαλίδας. Δείτε πώς:

```csharp
// Δημιουργήστε ένα αντικείμενο πίνακα
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Προσθέστε τον πίνακα στη συλλογή παραγράφων της ενότητας κεφαλίδας
header.Paragraphs.Add(tab1);

// Καθορίστε τα πλάτη των στηλών του πίνακα
tab1.ColumnWidths = "60,300";
```

Ο παραπάνω κώδικας δημιουργεί έναν πίνακα με δύο στήλες με καθορισμένα πλάτη.

## Βήμα 5: Προσθέστε γραμμές και κελιά στον πίνακα

 Τώρα θα προσθέσουμε γραμμές και κελιά στον πίνακα χρησιμοποιώντας το`Row` τάξη και το`Cell` τάξη. Δείτε πώς:

```csharp
// Δημιουργήστε μια σειρά στον πίνακα και προσθέστε κελιά
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Συγχωνεύστε το πρώτο κελί της πρώτης σειράς
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Δημιουργήστε μια άλλη σειρά στον πίνακα και προσθέστε ένα κελί με μια εικόνα
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Βήμα 6: Αποθήκευση του εγγράφου PDF

Μόλις προστεθεί ο πίνακας στην ενότητα κεφαλίδας, μπορούμε να αποθηκεύσουμε το έγγραφο PDF. Δείτε πώς:

```csharp
// Αποθηκεύστε το αρχείο PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Φροντίστε να αντικαταστήσετε το "YOUR DOCUMENTS DECTORY" με την πραγματική διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο PDF.

### Δείγμα πηγαίου κώδικα για την ενότητα υποσέλιδου πίνακα στην κεφαλίδα χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργήστε το στιγμιότυπο του εγγράφου καλώντας τον κενό κατασκευαστή
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Δημιουργήστε μια σελίδα στο έγγραφο pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// Δημιουργήστε μια ενότητα κεφαλίδας του αρχείου PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//Ορίστε την περιττή κεφαλίδα για το αρχείο PDF
page.Header = header;

// Ορίστε το επάνω περιθώριο για το τμήμα κεφαλίδας
header.Margin.Top = 20;

// Δημιουργήστε ένα αντικείμενο πίνακα
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Προσθέστε τον πίνακα στη συλλογή παραγράφων της επιθυμητής ενότητας
header.Paragraphs.Add(tab1);

// Ορίστε το προεπιλεγμένο περίγραμμα κελιού χρησιμοποιώντας το αντικείμενο BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Σετ με τα πλάτη στηλών του πίνακα
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Δημιουργήστε σειρές στον πίνακα και μετά κελιά στις σειρές
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Ορίστε την τιμή του εύρους γραμμής για την πρώτη σειρά ως 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Δημιουργήστε σειρές στον πίνακα και μετά κελιά στις σειρές
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Ορίστε το χρώμα φόντου για τη σειρά 2
row2.BackgroundColor = Color.White;

// Προσθέστε το κελί που περιέχει την εικόνα
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Ορίστε το πλάτος της εικόνας στο 60
img.FixWidth = 60;

// Προσθέστε την εικόνα στο κελί του πίνακα
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Ορίστε την κατακόρυφη στοίχιση του κειμένου ως στοίχιση στο κέντρο
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Αποθηκεύστε το αρχείο Pdf
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## συμπέρασμα

Συγχαρητήρια ! Έχετε μάθει πώς να προσθέτετε έναν πίνακα στην ενότητα κεφαλίδας ή υποσέλιδου ενός εγγράφου PDF χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε πλέον να προσαρμόσετε τις κεφαλίδες και τα υποσέλιδα σας προσθέτοντας πίνακες για να εμφανίζονται πρόσθετες πληροφορίες στα έγγραφα PDF.

### Συχνές ερωτήσεις για τον πίνακα στην ενότητα υποσέλιδου κεφαλίδας

#### Ε: Ποιος είναι ο σκοπός της προσθήκης ενός πίνακα στην ενότητα κεφαλίδας ή υποσέλιδου ενός εγγράφου PDF;

Α: Η προσθήκη πίνακα στην ενότητα κεφαλίδας ή υποσέλιδου ενός εγγράφου PDF σάς επιτρέπει να εμφανίζετε δομημένες και οργανωμένες πληροφορίες, όπως τίτλους, υπότιτλους, λογότυπα ή οποιοδήποτε άλλο περιεχόμενο που θέλετε να εμφανίζεται με συνέπεια σε κάθε σελίδα του εγγράφου.

#### Ε: Πώς ο παρεχόμενος πηγαίος κώδικας C# επιτυγχάνει την προσθήκη ενός πίνακα στην ενότητα κεφαλίδας ή υποσέλιδου ενός εγγράφου PDF;

Α: Ο κώδικας δείχνει τη διαδικασία δημιουργίας ενός κενού εγγράφου PDF, προσθήκης σελίδας, διαμόρφωσης της ενότητας κεφαλίδας, δημιουργίας πίνακα με σειρές και κελιά και, τέλος, αποθήκευση του εγγράφου PDF. Το αποτέλεσμα είναι ένας πίνακας που εμφανίζεται στην ενότητα κεφαλίδας του εγγράφου PDF.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση των κελιών του πίνακα, όπως περιγράμματα, χρώμα φόντου και στυλ κειμένου;

Α: Ναι, μπορείτε να προσαρμόσετε την εμφάνιση των κελιών του πίνακα ορίζοντας ιδιότητες όπως περιγράμματα κελιών, χρώμα φόντου, στυλ κειμένου, γραμματοσειρά, μέγεθος γραμματοσειράς και άλλα.

#### Ε: Πώς προστίθεται ο πίνακας στην ενότητα κεφαλίδας του εγγράφου PDF;

Α: Ο κώδικας προσθέτει τον πίνακα στη συλλογή παραγράφων της ενότητας κεφαλίδας, η οποία διασφαλίζει ότι ο πίνακας εμφανίζεται στην κεφαλίδα κάθε σελίδας.

#### Ε: Μπορώ να προσθέσω περισσότερες σειρές και κελιά στον πίνακα, όπως απαιτείται;

 Α: Οπωσδήποτε, μπορείτε να προσθέσετε περισσότερες σειρές και κελιά στον πίνακα χρησιμοποιώντας το`Rows.Add()` και`Cells.Add()` μεθόδους. Αυτό σας επιτρέπει να δομήσετε το περιεχόμενο του πίνακα όπως επιθυμείτε.

#### Ε: Είναι δυνατή η προσαρμογή του πλάτους των στηλών του πίνακα;
 Α: Ναι, μπορείτε να προσαρμόσετε το πλάτος των στηλών του πίνακα χρησιμοποιώντας το`ColumnWidths` ιδιοκτησία. Αυτό σας δίνει τη δυνατότητα να ελέγχετε τη διάταξη του πίνακα.

#### Ε: Πώς μπορώ να επεκταθώ σε κελιά σε πολλές στήλες ή σειρές μέσα στον πίνακα;
 Α: Για να εκτείνετε κελιά σε πολλές στήλες, μπορείτε να χρησιμοποιήσετε το`ColSpan` ιδιότητα του αντίστοιχου κελιού. Ομοίως, μπορείτε να χρησιμοποιήσετε το`RowSpan` ιδιότητα να καλύπτει κελιά σε πολλές σειρές.

#### Ε: Τι συμβαίνει εάν θέλω να προσθέσω έναν πίνακα και στις δύο ενότητες κεφαλίδας και υποσέλιδου του εγγράφου PDF;

Α: Μπορείτε να ακολουθήσετε παρόμοια προσέγγιση τόσο για τις ενότητες κεφαλίδας όσο και για το υποσέλιδο. Απλώς δημιουργήστε ένα`HeaderFooter` παράδειγμα για το υποσέλιδο, διαμορφώστε το και προσθέστε τον πίνακα στη συλλογή παραγράφων του.

#### Ε: Μπορώ να χρησιμοποιήσω εικόνες μέσα στα κελιά του πίνακα και πώς επιτυγχάνεται αυτό;

 Α: Ναι, μπορείτε να προσθέσετε εικόνες μέσα στα κελιά του πίνακα. Το παράδειγμα κώδικα δείχνει την προσθήκη μιας εικόνας σε ένα κελί με τη δημιουργία ενός`Image` αντικείμενο, ορίζοντας τη διαδρομή του αρχείου και τις διαστάσεις του και, στη συνέχεια, προσθέτοντάς το στις παραγράφους ενός κελιού.

#### Ε: Πώς μπορώ να διασφαλίσω ότι ο πίνακας εμφανίζεται με συνέπεια σε όλες τις σελίδες του εγγράφου PDF;

 Α: Όταν προσθέτετε τον πίνακα στην ενότητα κεφαλίδας ή υποσέλιδου χρησιμοποιώντας το`HeaderFooter` Για παράδειγμα, το Aspose.PDF διασφαλίζει ότι ο πίνακας εμφανίζεται με συνέπεια σε κάθε σελίδα, παρέχοντας ομοιόμορφη διάταξη.