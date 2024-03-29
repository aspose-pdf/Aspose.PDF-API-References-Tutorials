---
title: Σφραγίδες αριθμού σελίδας σε αρχείο PDF
linktitle: Σφραγίδες αριθμού σελίδας σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να προσθέτετε σφραγίδες αριθμού σελίδας σε αρχείο PDF με το Aspose.PDF για .NET.
type: docs
weight: 160
url: /el/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε βήμα προς βήμα για το πώς να προσθέσετε σφραγίδες αριθμού σελίδας σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα χρησιμοποιήσουμε τον παρεχόμενο πηγαίο κώδικα C# για να ανοίξουμε ένα υπάρχον έγγραφο PDF, να δημιουργήσουμε μια σφραγίδα αριθμού σελίδας, να ορίσουμε τις ιδιότητές του και να τον προσθέσουμε σε μια συγκεκριμένη σελίδα στο αρχείο PDF.

## Βήμα 1: Ρύθμιση περιβάλλοντος

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Ένα εγκατεστημένο περιβάλλον ανάπτυξης .NET.
- Η βιβλιοθήκη Aspose.PDF για .NET έγινε λήψη και αναφορά στο έργο σας.

## Βήμα 2: Φόρτωση του υπάρχοντος εγγράφου PDF

Το πρώτο βήμα είναι να φορτώσετε το υπάρχον έγγραφο PDF στο έργο σας. Δείτε πώς:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ανοίξτε το υπάρχον έγγραφο PDF
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την πραγματική διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφο PDF σας.

## Βήμα 3: Δημιουργία και διαμόρφωση της σφραγίδας αρίθμησης σελίδων

Τώρα που έχει φορτωθεί το έγγραφο PDF, μπορούμε να δημιουργήσουμε ένα buffer αρίθμησης σελίδων και να το διαμορφώσουμε σύμφωνα με τις ανάγκες μας. Δείτε πώς:

```csharp
// Δημιουργήστε ένα buffer αριθμού σελίδας
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Καθορίστε εάν το buffer βρίσκεται στο παρασκήνιο ή όχι
pageNumberStamp.Background = false;

// Μορφή του buffer αρίθμησης σελίδων
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Κάτω περιθώριο του buffer αρίθμησης σελίδων
pageNumberStamp.BottomMargin = 10;

// Οριζόντια στοίχιση του buffer αρίθμησης σελίδων
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Αριθμός έναρξης αρίθμησης σελίδων
pageNumberStamp.StartingNumber = 1;

// Ορισμός ιδιοτήτων κειμένου buffer αριθμού σελίδας
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Ο παραπάνω κώδικας δημιουργεί μια σφραγίδα αριθμού σελίδας με ιδιότητες όπως η μορφή αριθμού σελίδας, το κάτω περιθώριο, η οριζόντια στοίχιση, ο αριθμός έναρξης και οι ιδιότητες κειμένου.

## Βήμα 4: Προσθήκη της σφραγίδας αριθμού σελίδας σε μια συγκεκριμένη σελίδα

Μόλις διαμορφωθεί η σφραγίδα αριθμού σελίδας, μπορούμε να την προσθέσουμε σε μια συγκεκριμένη σελίδα του εγγράφου PDF. Δείτε πώς:

```csharp
// Προσθέστε το buffer αριθμού σελίδας σε μια συγκεκριμένη σελίδα
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Ο παραπάνω κώδικας προσθέτει τη σφραγίδα του αριθμού σελίδας στην πρώτη σελίδα του εγγράφου PDF. Μπορείτε να αλλάξετε τον αριθμό σελίδας όπως απαιτείται.

## Βήμα 5: Αποθήκευση του τροποποιημένου εγγράφου PDF

Μόλις προστεθεί η σφραγίδα του αριθμού σελίδας στο έγγραφο PDF, μπορούμε να αποθηκεύσουμε το τροποποιημένο έγγραφο PDF. Δείτε πώς:

```csharp
// Αποθηκεύστε το τροποποιημένο έγγραφο PDF
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Φροντίστε να αντικαταστήσετε το "YOUR DOCUMENTS DECTORY" με την πραγματική διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το επεξεργασμένο έγγραφο PDF.

### Δείγμα πηγαίου κώδικα για Σφραγίδες αριθμού σελίδας χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Άνοιγμα εγγράφου
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Δημιουργία σφραγίδας αριθμού σελίδας
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Αν η σφραγίδα είναι φόντο
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Ορισμός ιδιοτήτων κειμένου
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Προσθήκη σφραγίδας σε συγκεκριμένη σελίδα
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Αποθήκευση εγγράφου εξόδου
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## συμπέρασμα

Συγχαρητήρια ! Έχετε μάθει πώς να προσθέτετε σφραγίδες αριθμού σελίδας σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Τώρα μπορείτε να εξατομικεύσετε τα έγγραφα PDF προσθέτοντας σαφείς και ενημερωτικούς αριθμούς σελίδων.

### Συχνές ερωτήσεις για σφραγίδες αριθμού σελίδας σε αρχείο PDF

#### Ε: Τι είναι η σφραγίδα αριθμού σελίδας και πώς χρησιμοποιείται για την προσθήκη αριθμών σελίδων σε ένα αρχείο PDF;

Α: Η Σφραγίδα αριθμού σελίδας είναι μια δυνατότητα στο Aspose.PDF που σας επιτρέπει να προσθέτετε δυναμικούς αριθμούς σελίδων σε συγκεκριμένες σελίδες ενός εγγράφου PDF. Σε αυτό το σεμινάριο, αυτό επιτυγχάνεται με τη δημιουργία ενός αντικειμένου PageNumberStamp, τη διαμόρφωση των ιδιοτήτων του και την προσθήκη του σε μια καθορισμένη σελίδα.

#### Ε: Πώς ο παρεχόμενος πηγαίος κώδικας C# επιτυγχάνει την προσθήκη σφραγίδων αριθμού σελίδας σε ένα αρχείο PDF;

Α: Ο κώδικας δείχνει πώς να φορτώσετε ένα υπάρχον έγγραφο PDF, να δημιουργήσετε ένα PageNumberStamp, να ορίσετε διάφορες ιδιότητες (όπως μορφή, γραμματοσειρά, στοίχιση κ.λπ.) και, στη συνέχεια, να προσθέσετε τη σφραγίδα σε μια συγκεκριμένη σελίδα. Η σφραγίδα υπολογίζει αυτόματα τον συνολικό αριθμό σελίδων και εισάγει τους σωστούς αριθμούς σελίδων.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση του αριθμού σελίδας, όπως στυλ γραμματοσειράς, χρώμα και μέγεθος;

Α: Οπωσδήποτε, μπορείτε να προσαρμόσετε την εμφάνιση της σφραγίδας αριθμού σελίδας προσαρμόζοντας ιδιότητες όπως γραμματοσειρά, μέγεθος γραμματοσειράς, στυλ γραμματοσειράς (έντονη, πλάγια γραφή, κ.λπ.) και χρώμα κειμένου.

#### Ε: Είναι δυνατή η προσθήκη σφραγίδων αριθμού σελίδας σε πολλές σελίδες σε ένα έγγραφο PDF;

Α: Ναι, μπορείτε να προσθέσετε σφραγίδες αριθμού σελίδας σε πολλές σελίδες δημιουργώντας πολλά αντικείμενα PageNumberStamp και προσθέτοντας το καθένα στις επιθυμητές σελίδες.

#### Ε: Μπορώ να επιλέξω αν η σφραγίδα του αριθμού σελίδας θα εμφανίζεται ως μέρος του περιεχομένου της σελίδας ή ως στοιχείο φόντου;

 Α: Ναι, μπορείτε να ελέγξετε εάν η σφραγίδα του αριθμού σελίδας εμφανίζεται ως μέρος του περιεχομένου της σελίδας ή ως στοιχείο φόντου ορίζοντας το`Background` ιδιοκτησία του PageNumberStamp.

#### Ε: Πώς μπορώ να καθορίσω τη μορφή του αριθμού σελίδας, συμπεριλαμβανομένου του συνολικού αριθμού σελίδων;

 Α: Ο κώδικας χρησιμοποιεί το`Format`ιδιότητα του PageNumberStamp για να καθορίσετε τη μορφή του αριθμού σελίδας. Η μακροεντολή "# από" χρησιμοποιείται για την αντιπροσώπευση του συνολικού αριθμού σελίδων.

#### Ε: Τι θα συμβεί αν προσθέσω την ίδια σφραγίδα αριθμού σελίδας σε πολλές σελίδες;

Α: Η προσθήκη της ίδιας παρουσίας PageNumberStamp σε πολλές σελίδες θα εμφανίσει τους σωστούς αριθμούς σελίδων για κάθε σελίδα. Η σφραγίδα προσαρμόζει αυτόματα τον αριθμό σελίδας και τον συνολικό αριθμό σελίδων.

#### Ε: Μπορώ να προσθέσω σφραγίδες αριθμού σελίδας σε ενότητες κεφαλίδας ή υποσέλιδου ενός εγγράφου PDF;

Α: Ενώ τα PageNumberStamps συνήθως προστίθενται απευθείας στο περιεχόμενο της σελίδας, μπορείτε να χρησιμοποιήσετε το FloatingBox ή άλλες τεχνικές για να τα τοποθετήσετε σε ενότητες κεφαλίδας ή υποσέλιδου.

#### Ε: Πώς μπορώ να καθορίσω τη θέση της σφραγίδας αριθμού σελίδας στη σελίδα;

 Α: Το`BottomMargin` και`HorizontalAlignment` Οι ιδιότητες του PageNumberStamp σάς επιτρέπουν να ελέγχετε τη θέση της σφραγίδας μέσα στη σελίδα.

#### Ε: Τι γίνεται αν θέλω να ξεκινήσω την αρίθμηση σελίδων από διαφορετικό αριθμό και όχι από 1;

 Α: Μπορείτε να ορίσετε το`StartingNumber`ιδιότητα του PageNumberStamp για να καθορίσετε τον αριθμό της αρχικής σελίδας.