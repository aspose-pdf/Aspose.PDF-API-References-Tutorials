---
title: Τοποθέτηση κειμένου γύρω από την εικόνα σε αρχείο PDF
linktitle: Τοποθέτηση κειμένου γύρω από την εικόνα σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να τοποθετείτε κείμενο γύρω από μια εικόνα σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 260
url: /el/net/programming-with-text/placing-text-around-image/
---
Σε αυτό το σεμινάριο, θα εξηγήσουμε πώς να τοποθετήσετε κείμενο γύρω από μια εικόνα σε αρχείο PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Θα ακολουθήσουμε τη διαδικασία βήμα προς βήμα δημιουργίας πίνακα, προσθήκης εικόνας και τοποθέτησης κειμένου γύρω από την εικόνα χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα C#.

## Απαιτήσεις

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.PDF για .NET.
- Βασική κατανόηση του προγραμματισμού C#.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων

 Πρώτα, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το αρχείο PDF που δημιουργήθηκε. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στο`dataDir`μεταβλητή με τη διαδρομή προς τον επιθυμητό κατάλογο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα έγγραφο και μια σελίδα

 Στη συνέχεια, δημιουργούμε ένα`Document` αντικείμενο και προσθέστε μια σελίδα σε αυτό χρησιμοποιώντας το`Pages.Add()` μέθοδος.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Βήμα 3: Δημιουργήστε έναν πίνακα

 Δημιουργούμε έναν πίνακα χρησιμοποιώντας το`Table` τάξη και προσθέστε το στη συλλογή παραγράφων της σελίδας.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Βήμα 4: Ορίστε τα πλάτη και τα περιθώρια στηλών πίνακα

 Ορίζουμε τα πλάτη των στηλών του πίνακα και δημιουργούμε ένα`MarginInfo` αντικείμενο να ορίσετε τα περιθώρια.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Βήμα 5: Προσθέστε μια εικόνα στον πίνακα

 Δημιουργούμε ένα`Image` αντικείμενο, καθορίστε τη διαδρομή του αρχείου εικόνας και ορίστε το σταθερό ύψος και πλάτος της εικόνας. Στη συνέχεια, προσθέτουμε την εικόνα στη συλλογή παραγράφων του κελιού του πίνακα.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Βήμα 6: Προσθέστε κείμενο γύρω από την εικόνα

 Δημιουργούμε μεταβλητές συμβολοσειράς που περιέχουν κείμενο με μορφοποίηση HTML και δημιουργούμε ένα`HtmlFragment`αντικείμενο. Στη συνέχεια, προσθέτουμε το κείμενο HTML στο κελί του πίνακα που περιέχει την εικόνα.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Βήμα 7: Προσθήκη πρόσθετου κειμένου

 Δημιουργούμε ένα άλλο`HtmlFragment` αντικείμενο που περιέχει επιπλέον κείμενο με μορφοποίηση HTML και προσθέστε το σε ένα ξεχωριστό κελί πίνακα.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Βήμα 8: Αποθηκεύστε το έγγραφο PDF

Τέλος, αποθηκεύουμε το έγγραφο PDF στο καθορισμένο αρχείο εξόδου.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Δείγμα πηγαίου κώδικα για την τοποθέτηση κειμένου γύρω από την εικόνα χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Άμεσο αντικείμενο εγγράφου
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Δημιουργήστε μια σελίδα σε Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Δημιουργήστε ένα αντικείμενο πίνακα
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Προσθέστε τον πίνακα στη συλλογή παραγράφων της επιθυμητής ενότητας
page.Paragraphs.Add(table1);
// Σετ με τα πλάτη στηλών του πίνακα
table1.ColumnWidths = "120 270";
// Δημιουργήστε αντικείμενο MarginInfo και ορίστε τα περιθώρια αριστερά, κάτω, δεξιά και πάνω
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Ορίστε την προεπιλεγμένη συμπλήρωση κελιών στο αντικείμενο MarginInfo
table1.DefaultCellPadding = margin;
// Δημιουργήστε σειρές στον πίνακα και μετά κελιά στις σειρές
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Δημιουργήστε ένα αντικείμενο εικόνας
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Καθορίστε τη διαδρομή αρχείου εικόνας
logo.File = dataDir + "aspose-logo.jpg";
// Καθορίστε την εικόνα Σταθερό ύψος
logo.FixHeight = 120;
// Καθορίστε την εικόνα Σταθερό πλάτος
logo.FixWidth = 110;
row1.Cells.Add();
// Προσθέστε την εικόνα στη συλλογή παραγράφων του κελιού πίνακα
row1.Cells[0].Paragraphs.Add(logo);
// Δημιουργήστε μεταβλητές συμβολοσειράς με κείμενο που περιέχει ετικέτες html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Δημιουργήστε ένα αντικείμενο κειμένου που θα προστεθεί στα δεξιά της εικόνας
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Προσθέστε τις παραγράφους κειμένου που περιέχουν κείμενο HTML στο κελί του πίνακα
row1.Cells[1].Paragraphs.Add(TitleText);
// Ορίστε την κατακόρυφη στοίχιση των περιεχομένων της σειράς ως επάνω
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Δημιουργήστε σειρές στον πίνακα και μετά κελιά στις σειρές
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Ορίστε την τιμή του εύρους γραμμής για τη Δεύτερη σειρά ως 2
SecondRow.Cells[0].ColSpan = 2;
// Ορίστε την κατακόρυφη στοίχιση της δεύτερης σειράς ως επάνω
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Προσθέστε τις παραγράφους κειμένου που περιέχουν κείμενο HTML στο κελί του πίνακα
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Αποθηκεύστε το αρχείο Pdf
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## συμπέρασμα

Σε αυτό το σεμινάριο, έχετε μάθει πώς να τοποθετείτε κείμενο γύρω από μια εικόνα σε ένα έγγραφο PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα και εκτελώντας τον παρεχόμενο κώδικα C#, μπορείτε να δημιουργήσετε έναν πίνακα, να προσθέσετε μια εικόνα και να τοποθετήσετε κείμενο γύρω από την εικόνα σε ένα έγγραφο PDF.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός του σεμιναρίου "Τοποθέτηση κειμένου γύρω από την εικόνα σε αρχείο PDF";

Α: Το σεμινάριο "Τοποθέτηση κειμένου γύρω από την εικόνα σε αρχείο PDF" δείχνει πώς να χρησιμοποιήσετε τη βιβλιοθήκη Aspose.PDF για .NET για να τοποθετήσετε κείμενο γύρω από μια εικόνα σε ένα έγγραφο PDF. Το σεμινάριο παρέχει έναν οδηγό βήμα προς βήμα και τον πηγαίο κώδικα C# για να σας βοηθήσει να δημιουργήσετε έναν πίνακα, να προσθέσετε μια εικόνα και να τοποθετήσετε κείμενο γύρω από την εικόνα.

#### Ε: Γιατί θα ήθελα να τοποθετήσω κείμενο γύρω από μια εικόνα σε ένα έγγραφο PDF;

Α: Η τοποθέτηση κειμένου γύρω από μια εικόνα βελτιώνει την οπτική παρουσίαση των εγγράφων PDF σας, καθιστώντας τα πιο ελκυστικά και ενημερωτικά. Αυτή η τεχνική χρησιμοποιείται συχνά σε έγγραφα, φυλλάδια, αναφορές και άλλο υλικό όπου θέλετε να συνδυάσετε εικόνες και κείμενο με αισθητικά ευχάριστο τρόπο.

#### Ε: Πώς μπορώ να ρυθμίσω τον κατάλογο εγγράφων;

Α: Για να ρυθμίσετε τον κατάλογο εγγράφων:

1.  Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στο`dataDir` μεταβλητή με τη διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το αρχείο PDF που δημιουργήθηκε.

#### Ε: Πώς μπορώ να δημιουργήσω έναν πίνακα και να προσθέσω μια εικόνα σε αυτόν;

 Α: Το σεμινάριο σας καθοδηγεί στη διαδικασία δημιουργίας πίνακα χρησιμοποιώντας το`Table` τάξη και προσθέτοντας μια εικόνα στον πίνακα χρησιμοποιώντας το`Image` τάξη. Θα καθορίσετε τη διαδρομή, το ύψος και το πλάτος του αρχείου εικόνας πριν το προσθέσετε σε ένα κελί πίνακα.

#### Ε: Πώς τοποθετώ το κείμενο γύρω από την εικόνα;

 Α: Για να τοποθετήσετε κείμενο γύρω από την εικόνα, θα δημιουργήσετε κείμενο με μορφοποίηση HTML χρησιμοποιώντας το`HtmlFragment` τάξη. Αυτό το κείμενο θα περιέχει τόσο κείμενο τίτλου όσο και κύριου κειμένου. Στη συνέχεια, θα προσθέσετε αυτό το κείμενο HTML σε ένα κελί πίνακα που βρίσκεται δίπλα στο κελί της εικόνας.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση του κειμένου και της εικόνας;

Α: Ναι, μπορείτε να προσαρμόσετε την εμφάνιση του κειμένου και της εικόνας χρησιμοποιώντας ετικέτες και ιδιότητες HTML. Για παράδειγμα, μπορείτε να ορίσετε μεγέθη γραμματοσειράς, χρώματα, στυλ και στοίχιση για το κείμενο. Επιπλέον, μπορείτε να προσαρμόσετε το μέγεθος και τις διαστάσεις της εικόνας.

#### Ε: Πώς μπορώ να αποθηκεύσω το έγγραφο PDF;

 Α: Αφού προσθέσετε την εικόνα και το κείμενο στον πίνακα, μπορείτε να αποθηκεύσετε το έγγραφο PDF χρησιμοποιώντας το`Save` μέθοδος του`Document` τάξη. Δώστε την επιθυμητή διαδρομή αρχείου εξόδου ως όρισμα στο`Save` μέθοδος.

#### Ε: Ποιο είναι το αναμενόμενο αποτέλεσμα αυτού του σεμιναρίου;

Α: Ακολουθώντας το σεμινάριο και εκτελώντας τον παρεχόμενο κώδικα C#, θα δημιουργήσετε ένα έγγραφο PDF που δείχνει πώς να τοποθετείτε κείμενο γύρω από μια εικόνα. Το έγγραφο εξόδου θα περιέχει έναν πίνακα με μια εικόνα και κείμενο τοποθετημένα γύρω του.

#### Ε: Μπορώ να χρησιμοποιήσω διαφορετικές μορφές εικόνας εκτός από JPG;

 Α: Ναι, μπορείτε να χρησιμοποιήσετε διαφορετικές μορφές εικόνας που υποστηρίζονται από τη βιβλιοθήκη Aspose.PDF, όπως PNG, BMP, GIF και άλλα. Κατά τη δημιουργία του`Image` αντικείμενο, καθορίστε τη διαδρομή αρχείου της επιθυμητής μορφής εικόνας.

#### Ε: Απαιτείται έγκυρη άδεια Aspose για αυτό το σεμινάριο;

Α: Ναι, απαιτείται έγκυρη άδεια Aspose για να λειτουργήσει σωστά αυτό το σεμινάριο. Μπορείτε να αγοράσετε μια πλήρη άδεια χρήσης ή να αποκτήσετε μια προσωρινή άδεια 30 ημερών από τον ιστότοπο Aspose.