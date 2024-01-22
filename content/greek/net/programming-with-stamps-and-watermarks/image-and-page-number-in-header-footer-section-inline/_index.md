---
title: Εικόνα και αριθμός σελίδας στην Ενότητα Υποσέλιδο κεφαλίδας Ενσωματωμένη
linktitle: Εικόνα και αριθμός σελίδας στην Ενότητα Υποσέλιδο κεφαλίδας Ενσωματωμένη
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να προσθέτετε εικόνα και αριθμό σελίδας στην κεφαλίδα και το υποσέλιδο χρησιμοποιώντας ενσωματωμένες παραγράφους με το Aspose.PDF για .NET.
type: docs
weight: 120
url: /el/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε βήμα προς βήμα σχετικά με τον τρόπο προσθήκης εικόνας και αριθμού σελίδας στην ενότητα κεφαλίδας και υποσέλιδου του εγγράφου PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα χρησιμοποιήσουμε τον παρεχόμενο πηγαίο κώδικα C# για να δημιουργήσουμε μια σελίδα, να ορίσουμε κεφαλίδα και υποσέλιδο, να προσθέσουμε εικόνα και κείμενο χρησιμοποιώντας ενσωματωμένες παραγράφους στην κεφαλίδα του εγγράφου PDF.

## Βήμα 1: Ρύθμιση περιβάλλοντος

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Ένα εγκατεστημένο περιβάλλον ανάπτυξης .NET.
- Η βιβλιοθήκη Aspose.PDF για .NET έγινε λήψη και αναφορά στο έργο σας.

## Βήμα 2: Δημιουργία του εγγράφου και της σελίδας PDF

Το πρώτο βήμα είναι να δημιουργήσετε ένα νέο αντικείμενο Document και μια σελίδα στο έγγραφο PDF. Δείτε πώς:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργήστε ένα νέο αντικείμενο Document
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Δημιουργήστε μια σελίδα στο έγγραφο
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Ο παραπάνω κώδικας δημιουργεί ένα νέο αντικείμενο Document και μια κενή σελίδα στο έγγραφο PDF.

## Βήμα 3: Προσθήκη της κεφαλίδας με εικόνα και ενσωματωμένο κείμενο

Τώρα που δημιουργείται η σελίδα, μπορούμε να προσθέσουμε μια ενότητα κεφαλίδας με εικόνα και κείμενο χρησιμοποιώντας ενσωματωμένες παραγράφους. Δείτε πώς:

```csharp
// Δημιουργήστε μια ενότητα κεφαλίδας
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ορίστε την κεφαλίδα της σελίδας
page. Header = header;

// Δημιουργήστε ένα αντικείμενο TextFragment για το πρώτο ενσωματωμένο κείμενο
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Καθορίστε το χρώμα του κειμένου
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Δημιουργήστε ένα αντικείμενο εικόνας για την εικόνα
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Ορισμός διαδρομής εικόνας
image1.File = dataDir + "aspose-logo.jpg";

// Καθορίστε τις διαστάσεις της εικόνας
image1.FixWidth = 50;
image1.FixHeight = 20;

// Υποδείξτε ότι το πρώτο ενσωματωμένο κείμενο είναι εικόνα
image1.IsInLineParagraph = true;

// Δημιουργήστε ένα δεύτερο ενσωματωμένο κείμενο
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Προσθήκη στοιχείων στην κεφαλίδα
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Ο παραπάνω κώδικας δημιουργεί μια ενότητα κεφαλίδας, ορίζει την κεφαλίδα της σελίδας με αυτήν την ενότητα, προσθέτει ένα TextFragment με ενσωματωμένο κείμενο και ένα αντικείμενο ενσωματωμένης εικόνας.

## Βήμα 4: Αποθήκευση του τροποποιημένου εγγράφου PDF

Μόλις προστεθεί η κεφαλίδα με την εικόνα και το ενσωματωμένο κείμενο, μπορούμε να αποθηκεύσουμε το τροποποιημένο έγγραφο PDF. Δείτε πώς:

```csharp
// Αποθηκεύστε το τροποποιημένο έγγραφο PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Ο παραπάνω κώδικας αποθηκεύει το επεξεργασμένο έγγραφο PDF στον καθορισμένο κατάλογο.

### Δείγμα πηγαίου κώδικα για Imageand Page Numberin Header Footersection Inline χρησιμοποιώντας Aspose.PDF για .NET 
```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργήστε ένα αντικείμενο Document καλώντας τον κενό κατασκευαστή του
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Δημιουργήστε μια σελίδα στο αντικείμενο Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Δημιουργία ενότητας κεφαλίδας του εγγράφου
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ορίστε την κεφαλίδα για το αρχείο PDF
page.Header = header;

// Δημιουργήστε ένα αντικείμενο κειμένου
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Προσδιορίστε το χρώμα
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Δημιουργήστε ένα αντικείμενο εικόνας στην ενότητα
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Ορίστε τη διαδρομή του αρχείου εικόνας
image1.File = dataDir + "aspose-logo.jpg";

// Ορίστε το πλάτος της εικόνας Πληροφορίες
image1.FixWidth = 50;
image1.FixHeight = 20;

// Υποδείξτε ότι το InlineParagraph του seg1 είναι μια εικόνα.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Αποθηκεύστε το Pdf
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## συμπέρασμα

Συγχαρητήρια ! Μάθατε πώς να προσθέτετε μια εικόνα και έναν αριθμό σελίδας στην ενότητα κεφαλίδας και υποσέλιδου ενός εγγράφου PDF χρησιμοποιώντας ενσωματωμένες παραγράφους με το Aspose.PDF για .NET. Τώρα μπορείτε να προσαρμόσετε την κεφαλίδα και το υποσέλιδο των εγγράφων PDF σας με ευελιξία.

### Συχνές ερωτήσεις

#### Ε: Ποιο είναι το πλεονέκτημα της χρήσης ενσωματωμένων παραγράφων για την προσθήκη εικόνας και κειμένου στην κεφαλίδα ενός εγγράφου PDF;

Α: Η χρήση ενσωματωμένων παραγράφων σάς επιτρέπει να ενσωματώνετε απρόσκοπτα εικόνες και κείμενο στην ίδια παράγραφο, παρέχοντας ακριβή έλεγχο της τοποθέτησης και της μορφοποίησής τους. Αυτή η μέθοδος είναι ιδιαίτερα χρήσιμη για τη δημιουργία προσαρμοσμένων κεφαλίδων με οπτικά στοιχεία.

#### Ε: Πώς ο παρεχόμενος πηγαίος κώδικας C# επιτυγχάνει ενσωματωμένες παραγράφους για την κεφαλίδα σε ένα έγγραφο PDF;

Α: Ο παρεχόμενος κώδικας δείχνει πώς να δημιουργήσετε ένα έγγραφο PDF, να προσθέσετε μια σελίδα και να προσαρμόσετε την κεφαλίδα χρησιμοποιώντας ενσωματωμένες παραγράφους. Προσθέτει ένα TextFragment με ενσωματωμένο κείμενο, μια ενσωματωμένη εικόνα και ένα άλλο ενσωματωμένο TextFragment.

#### Ε: Πώς μπορώ να καθορίσω το χρώμα του ενσωματωμένου κειμένου στην κεφαλίδα;

 A: Το χρώμα του ενσωματωμένου κειμένου καθορίζεται χρησιμοποιώντας το`ForegroundColor` ιδιοκτησία του`TextState` απο`TextFragment` αντικείμενο.

#### Ε: Μπορώ να προσαρμόσω τις διαστάσεις της ενσωματωμένης εικόνας στην κεφαλίδα;

 Α: Ναι, μπορείτε να προσαρμόσετε τις διαστάσεις της ενσωματωμένης εικόνας χρησιμοποιώντας το`FixWidth` και`FixHeight` ιδιότητες του`Image` αντικείμενο. Αυτό σας επιτρέπει να ελέγχετε το πλάτος και το ύψος της εικόνας εντός της κεφαλίδας.

#### Ε: Μπορώ να συμπεριλάβω πρόσθετα ενσωματωμένα στοιχεία, όπως υπερσυνδέσμους ή διαφορετικά στυλ γραμματοσειράς, στην κεφαλίδα;

 Α: Ναι, μπορείτε να συμπεριλάβετε πρόσθετα ενσωματωμένα στοιχεία στην κεφαλίδα δημιουργώντας περισσότερα`TextFragment` ή`Image` αντικείμενα με τις επιθυμητές ιδιότητες. Αυτό σας επιτρέπει να προσαρμόσετε περαιτέρω την κεφαλίδα, συμπεριλαμβανομένων υπερσυνδέσμων, διαφορετικών στυλ γραμματοσειράς ή άλλων οπτικών στοιχείων.

#### Ε: Πώς μπορώ να διασφαλίσω ότι η ενσωματωμένη εικόνα και κείμενο παραμένουν σωστά ευθυγραμμισμένα και μορφοποιημένα σε διαφορετικές συσκευές και προγράμματα προβολής;

Α: Το Aspose.PDF για .NET διασφαλίζει ότι οι ενσωματωμένες εικόνες και το κείμενο είναι σωστά ευθυγραμμισμένες και μορφοποιημένες, με αποτέλεσμα τη συνεπή εμφάνιση σε διαφορετικές συσκευές και προγράμματα προβολής PDF.

#### Ε: Μπορώ να εφαρμόσω ενσωματωμένες παραγράφους και στην ενότητα του υποσέλιδου;

 Α: Ναι, μπορείτε να εφαρμόσετε την ίδια τεχνική χρήσης ενσωματωμένων παραγράφων στην ενότητα υποσέλιδου δημιουργώντας ένα`Footer` αντικείμενο και προσθήκη ενσωματωμένων στοιχείων όπως κείμενο και εικόνες σε αυτό.

#### Ε: Είναι δυνατός ο συνδυασμός ενσωματωμένων παραγράφων με άλλες μεθόδους προσαρμογής κεφαλίδας ή υποσέλιδου;

Α: Ναι, μπορείτε να συνδυάσετε ενσωματωμένες παραγράφους με άλλες μεθόδους προσαρμογής κεφαλίδας ή υποσέλιδου που παρέχονται από το Aspose.PDF για .NET για να δημιουργήσετε πιο σύνθετα και προσαρμοσμένα σχέδια κεφαλίδας ή υποσέλιδου.

#### Ε: Μπορώ να αφαιρέσω ή να διαγράψω τα ενσωματωμένα στοιχεία από την κεφαλίδα εάν χρειάζεται;

 Α: Ναι, μπορείτε να αφαιρέσετε ή να διαγράψετε τα ενσωματωμένα στοιχεία τροποποιώντας τα περιεχόμενα του`HeaderFooter` αντικείμενο και αφαιρώντας τις αντίστοιχες ενσωματωμένες παραγράφους.

#### Ε: Πώς μπορώ να εφαρμόσω ενσωματωμένες παραγράφους σε συγκεκριμένες σελίδες του εγγράφου PDF;

 Α: Για να εφαρμόσετε ενσωματωμένες παραγράφους σε συγκεκριμένες σελίδες, μπορείτε να δημιουργήσετε ξεχωριστές`HeaderFooter` αντικείμενα για κάθε σελίδα και αντιστοιχίστε τα χρησιμοποιώντας το`Header` ιδιοκτησία του αντίστοιχου`Aspose.Pdf.Page` αντικείμενα.