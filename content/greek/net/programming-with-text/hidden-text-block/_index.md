---
title: Κρυφό μπλοκ κειμένου σε αρχείο PDF
linktitle: Κρυφό μπλοκ κειμένου σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να δημιουργείτε κρυφά μπλοκ κειμένου σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 230
url: /el/net/programming-with-text/hidden-text-block/
---
Σε αυτό το σεμινάριο, θα εξηγήσουμε πώς να δημιουργήσετε ένα κρυφό μπλοκ κειμένου σε αρχείο PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Ένα κρυφό μπλοκ κειμένου είναι ένα αιωρούμενο κείμενο που γίνεται ορατό όταν ο κέρσορας του ποντικιού αιωρείται σε μια συγκεκριμένη περιοχή. Θα ακολουθήσουμε τη διαδικασία βήμα προς βήμα δημιουργίας του κρυφού μπλοκ κειμένου χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα C#.

## Απαιτήσεις

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.PDF για .NET.
- Βασική κατανόηση του προγραμματισμού C#.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων

 Πρώτα, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το αρχείο PDF που δημιουργήθηκε. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στο`dataDir` μεταβλητή με τη διαδρομή προς τον επιθυμητό κατάλογο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα δείγμα εγγράφου

Σε αυτό το βήμα, δημιουργούμε ένα δείγμα εγγράφου PDF και προσθέτουμε ένα τμήμα κειμένου σε αυτό. Το τμήμα κειμένου θα χρησιμεύσει ως το έναυσμα για την εμφάνιση του κρυφού μπλοκ κειμένου.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Βήμα 3: Ανοίξτε το Έγγραφο

 Τώρα, ανοίγουμε το έγγραφο που δημιουργήθηκε προηγουμένως χρησιμοποιώντας το`Document` τάξη.

```csharp
Document document = new Document(outputFile);
```

## Βήμα 4: Βρείτε το Τμήμα κειμένου

 Χρησιμοποιούμε α`TextFragmentAbsorber`αντικείμενο για να βρείτε το τμήμα κειμένου που θα ενεργοποιήσει την εμφάνιση του κρυφού μπλοκ κειμένου. Σε αυτήν την περίπτωση, αναζητούμε το ακριβές κείμενο "Μετακινήστε τον κέρσορα του ποντικιού εδώ για εμφάνιση αιωρούμενου κειμένου".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Βήμα 5: Δημιουργήστε το κρυφό πεδίο κειμένου

 Δημιουργούμε α`TextBoxField` αντικείμενο για να αναπαραστήσει το κρυφό πεδίο κειμένου. Αυτό το πεδίο θα περιέχει το κείμενο που γίνεται ορατό όταν ο κέρσορας του ποντικιού τοποθετείται πάνω από το κείμενο σκανδάλης.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Βήμα 6: Προσθέστε το κρυφό πεδίο κειμένου στο έγγραφο

Προσθέτουμε το πεδίο κρυφού κειμένου στη συλλογή φορμών του εγγράφου.

```csharp
document.Form.Add(floatingField);
```

## Βήμα 7: Δημιουργήστε το αόρατο κουμπί

Δημιουργούμε ένα αόρατο πεδίο κουμπιού που θα τοποθετηθεί στην κορυφή του τμήματος κειμένου ενεργοποίησης. Αυτό το πεδίο κουμπιού θα έχει ενέργειες που σχετίζονται με συμβάντα εισαγωγής και εξόδου του ποντικιού.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Βήμα 8: Αποθηκεύστε το έγγραφο

Τέλος, αποθηκεύουμε το τροποποιημένο έγγραφο με το κρυφό μπλοκ κειμένου.

```csharp
document. Save(outputFile);
```

### Δείγμα πηγαίου κώδικα για το μπλοκ κρυφού κειμένου χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Δημιουργία δείγματος εγγράφου με κείμενο
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Άνοιγμα εγγράφου με κείμενο
Document document = new Document(outputFile);
// Δημιουργήστε αντικείμενο TextAbsorber για να βρείτε όλες τις φράσεις που ταιριάζουν με την κανονική έκφραση
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Αποδεχτείτε τον απορροφητήρα για τις σελίδες του εγγράφου
document.Pages.Accept(absorber);
// Λάβετε το πρώτο εξαγόμενο τμήμα κειμένου
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//Δημιουργήστε κρυφό πεδίο κειμένου για αιωρούμενο κείμενο στο καθορισμένο ορθογώνιο της σελίδας
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Ορίστε το κείμενο που θα εμφανίζεται ως τιμή πεδίου
floatingField.Value = "This is the \"floating text field\".";
// Συνιστούμε να κάνετε το πεδίο "μόνο για ανάγνωση" για αυτό το σενάριο
floatingField.ReadOnly = true;
// Ορίστε την «κρυφή» σημαία για να κάνετε το πεδίο αόρατο στο άνοιγμα του εγγράφου
floatingField.Flags |= AnnotationFlags.Hidden;
// Ο ορισμός ενός μοναδικού ονόματος πεδίου δεν είναι απαραίτητος αλλά επιτρέπεται
floatingField.PartialName = "FloatingField_1";
// Ο καθορισμός χαρακτηριστικών εμφάνισης πεδίου δεν είναι απαραίτητος, αλλά το κάνει καλύτερο
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Προσθήκη πεδίου κειμένου στο έγγραφο
document.Form.Add(floatingField);
// Δημιουργία αόρατου κουμπιού στη θέση του τμήματος κειμένου
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Δημιουργήστε νέα ενέργεια απόκρυψης για καθορισμένο πεδίο (σχολιασμός) και σημαία αορατότητας.
// (Μπορείτε επίσης να αναφέρετε το κυμαινόμενο πεδίο με το όνομα εάν το προσδιορίσατε παραπάνω.)
// Προσθέστε ενέργειες στην είσοδο/έξοδο του ποντικιού στο πεδίο του αόρατου κουμπιού
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Προσθήκη πεδίου κουμπιού στο έγγραφο
document.Form.Add(buttonField);
// Αποθήκευση εγγράφου
document.Save(outputFile);
```

## Σύναψη

Σε αυτό το σεμινάριο, έχετε μάθει πώς να δημιουργείτε ένα κρυφό μπλοκ κειμένου χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να δημιουργήσετε ένα έγγραφο PDF με ένα κρυφό πεδίο κειμένου που γίνεται ορατό όταν ο κέρσορας του ποντικιού αιωρείται σε μια συγκεκριμένη περιοχή. Μπορείτε να προσαρμόσετε την εμφάνιση και τη συμπεριφορά του μπλοκ κρυφού κειμένου σύμφωνα με τις απαιτήσεις σας.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός του σεμιναρίου "Κρυφό μπλοκ κειμένου σε αρχείο PDF";

Α: Το σεμινάριο "Hidden Text Block In PDF File" εξηγεί πώς να δημιουργήσετε ένα κρυφό μπλοκ κειμένου σε ένα αρχείο PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Ένα κρυφό μπλοκ κειμένου είναι ένα αιωρούμενο κείμενο που γίνεται ορατό όταν ο κέρσορας του ποντικιού αιωρείται σε μια συγκεκριμένη περιοχή. Αυτό το σεμινάριο παρέχει έναν οδηγό βήμα προς βήμα χρησιμοποιώντας τον πηγαίο κώδικα C#.

#### Ε: Γιατί θα ήθελα να δημιουργήσω ένα κρυφό μπλοκ κειμένου σε ένα αρχείο PDF;

Α: Η δημιουργία ενός κρυφού μπλοκ κειμένου μπορεί να είναι χρήσιμη για διαδραστικά έγγραφα PDF όπου θέλετε να παρέχετε πρόσθετες πληροφορίες ή περιβάλλον που γίνονται ορατά μόνο όταν ένας χρήστης τοποθετεί τον κέρσορα του ποντικιού πάνω σε μια καθορισμένη περιοχή.

#### Ε: Πώς μπορώ να ρυθμίσω τον κατάλογο εγγράφων;

Α: Για να ρυθμίσετε τον κατάλογο εγγράφων:

1.  Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στο`dataDir` μεταβλητή με τη διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το αρχείο PDF που δημιουργήθηκε.

#### Ε: Πώς μπορώ να δημιουργήσω ένα δείγμα εγγράφου και να προσθέσω ένα τμήμα κειμένου σε αυτό;

 Α: Στο σεμινάριο, χρησιμοποιείτε το`Document` τάξη για να δημιουργήσετε ένα δείγμα εγγράφου PDF και να προσθέσετε ένα τμήμα κειμένου. Αυτό το τμήμα κειμένου χρησιμεύει ως το έναυσμα για την εμφάνιση του κρυφού μπλοκ κειμένου.

#### Ε: Πώς μπορώ να βρω το τμήμα κειμένου που ενεργοποιεί το μπλοκ κρυφού κειμένου;

 Α: Το σεμινάριο δείχνει πώς να χρησιμοποιήσετε το α`TextFragmentAbsorber` αντικείμενο για να βρείτε το τμήμα κειμένου που ενεργοποιεί την εμφάνιση του κρυφού μπλοκ κειμένου. Αναζητά μια συγκεκριμένη συμβολοσειρά κειμένου μέσα στο έγγραφο PDF.

#### Ε: Πώς μπορώ να δημιουργήσω και να προσαρμόσω το πεδίο κρυφού κειμένου;

 Α: Δημιουργείτε ένα`TextBoxField`αντικείμενο για να αναπαραστήσει το κρυφό πεδίο κειμένου. Το σεμινάριο παρέχει κώδικα για να ορίσετε διάφορες ιδιότητες, όπως θέση, τιμή, εμφάνιση και συμπεριφορά του πεδίου κρυφού κειμένου.

#### Ε: Πώς μπορώ να δημιουργήσω ένα αόρατο κουμπί που σχετίζεται με το μπλοκ κρυφού κειμένου;

 A: Δημιουργείται ένα αόρατο πεδίο κουμπιού χρησιμοποιώντας το`ButtonField` τάξη. Αυτό το πεδίο κουμπιού είναι τοποθετημένο στην κορυφή του τμήματος κειμένου ενεργοποίησης και έχει ενέργειες που σχετίζονται με συμβάντα εισαγωγής και εξόδου του ποντικιού. Αυτές οι ενέργειες ελέγχουν την ορατότητα του κρυφού μπλοκ κειμένου.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση του κρυφού μπλοκ κειμένου και της περιοχής ενεργοποίησης;

Α: Ναι, μπορείτε να προσαρμόσετε διάφορες ιδιότητες τόσο του πεδίου κρυφού κειμένου όσο και του αόρατου κουμπιού, συμπεριλαμβανομένης της γραμματοσειράς, του χρώματος, του μεγέθους και της θέσης.

#### Ε: Πώς μπορώ να αποθηκεύσω το τροποποιημένο έγγραφο με το κρυφό μπλοκ κειμένου;

 Α: Το σεμινάριο δείχνει πώς να αποθηκεύσετε το τροποποιημένο έγγραφο χρησιμοποιώντας το`Save` μέθοδος του`Document` τάξη.