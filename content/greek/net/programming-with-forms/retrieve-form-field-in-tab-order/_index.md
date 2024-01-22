---
title: Ανάκτηση πεδίου φόρμας με σειρά καρτελών
linktitle: Ανάκτηση πεδίου φόρμας με σειρά καρτελών
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να ανακτάτε τα πεδία φόρμας με σειρά καρτελών χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 240
url: /el/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Όταν εργάζεστε με έγγραφα PDF σε C# χρησιμοποιώντας το Aspose.PDF για .NET, ενδέχεται να συναντήσετε ένα σενάριο όπου πρέπει να ανακτήσετε πεδία φόρμας με μια συγκεκριμένη σειρά καρτελών. Αυτό μπορεί να είναι χρήσιμο όταν θέλετε να εκτελέσετε λειτουργίες σε πεδία φόρμας με βάση τη σειρά καρτελών τους. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε βήμα προς βήμα σχετικά με τον τρόπο ανάκτησης πεδίων φόρμας με σειρά καρτελών χρησιμοποιώντας το Aspose.PDF για .NET.

## Απαιτήσεις

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Το Visual Studio είναι εγκατεστημένο στο σύστημά σας
- Εγκαταστάθηκε το Aspose.PDF για τη βιβλιοθήκη .NET

Τώρα, ας βουτήξουμε στα βήματα για την ανάκτηση των πεδίων φόρμας με τη σειρά των καρτελών.

## Βήμα 1: Ρύθμιση του καταλόγου εγγράφων

 Αρχικά, πρέπει να ορίσετε τον κατάλογο εγγράφων όπου βρίσκεται το έγγραφο PDF. Μπορείτε να το κάνετε αυτό καθορίζοντας τη διαδρομή προς τον κατάλογο στο`dataDir` μεταβλητός.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

## Βήμα 2: Φόρτωση του εγγράφου PDF

 Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. ο`Document` class παρέχει τη δυνατότητα φόρτωσης και χειρισμού εγγράφων PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Εδώ,`"Test2.pdf"`είναι το όνομα του εγγράφου PDF που θέλετε να φορτώσετε. Βεβαιωθείτε ότι το έγγραφο υπάρχει στον καθορισμένο κατάλογο εγγράφων.

## Βήμα 3: Ανάκτηση πεδίων φόρμας με σειρά καρτελών

 Για να ανακτήσουμε τα πεδία φόρμας με τη σειρά των καρτελών, πρέπει να έχουμε πρόσβαση στο`FieldsInTabOrder` ιδιοκτησία του`Page` τάξη. Αυτή η ιδιότητα επιστρέφει μια λίστα πεδίων φόρμας ταξινομημένα με βάση τη σειρά καρτελών τους.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Στο παραπάνω απόσπασμα κώδικα, ανακτούμε τα πεδία φόρμας από τη δεύτερη σελίδα (`doc.Pages[1]` ) και επαναλάβετε μέσα από κάθε πεδίο για να συνδέσετε τα επιμέρους ονόματά τους στο`s` μεταβλητός. Μπορείτε να τροποποιήσετε αυτό το απόσπασμα κώδικα με βάση τις συγκεκριμένες απαιτήσεις σας.

## Βήμα 4: Τροποποίηση της σειράς καρτελών

 Εάν θέλετε να τροποποιήσετε τη σειρά των καρτελών των πεδίων φόρμας, μπορείτε να το κάνετε μεταβαίνοντας στο`TabOrder` ιδιότητα κάθε πεδίου και εκχώρηση τιμής σειράς νέας καρτέλας. Εδώ είναι ένα παράδειγμα:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Στο παραπάνω απόσπασμα κώδικα, εκχωρούμε τιμές σειράς νέων καρτελών σε τρία πεδία φόρμας (`doc.Form[3]`, `doc.Form[1]` , και`doc.Form[2]`). Προσαρμόστε τους δείκτες πεδίων και τις τιμές σειράς καρτελών σύμφωνα με τις συγκεκριμένες απαιτήσεις σας.

## Βήμα 5: Αποθήκευση του τροποποιημένου εγγράφου

 Αφού τροποποιήσετε τη σειρά των καρτελών των πεδίων φόρμας, πρέπει να αποθηκεύσετε το τροποποιημένο έγγραφο. Μπορείτε να το κάνετε αυτό χρησιμοποιώντας το`Save` μέθοδος του`Document` τάξη.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Εδώ,`"39522_out.pdf"` είναι το όνομα του αρχείου εξόδου όπου θα αποθηκευτεί το τροποποιημένο έγγραφο. Καθορίστε το επιθυμητό όνομα και θέση για το αρχείο εξόδου.

### Δείγμα πηγαίου κώδικα για Ανάκτηση Πεδίου Φόρμας σε Σειρά καρτελών χρησιμοποιώντας Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να ανακτούμε τα πεδία φόρμας με σειρά καρτελών χρησιμοποιώντας το Aspose.PDF για .NET. Καλύψαμε τα βήματα που απαιτούνται για τη φόρτωση ενός εγγράφου PDF, την ανάκτηση πεδίων φόρμας με σειρά καρτελών, την τροποποίηση της σειράς καρτελών και την αποθήκευση του τροποποιημένου εγγράφου. Ακολουθώντας αυτά τα βήματα, μπορείτε να εργαστείτε αποτελεσματικά με πεδία φόρμας και να προσαρμόσετε τη σειρά των καρτελών τους σύμφωνα με τις απαιτήσεις σας.


### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να χρησιμοποιήσω τα ανακτημένα πεδία φόρμας στον κώδικα C# για περαιτέρω επεξεργασία;

 Α: Μπορείτε να χρησιμοποιήσετε τα ανακτημένα πεδία φόρμας στον κώδικα C#, αποκτώντας πρόσβαση στις ιδιότητες τους, όπως π.χ`Value`, `Name`, `Rect`κ.λπ. Αυτές οι ιδιότητες σάς επιτρέπουν να διαβάζετε και να τροποποιείτε τα δεδομένα του πεδίου φόρμας όπως απαιτείται.

#### Ε: Μπορώ να ανακτήσω πεδία φόρμας από όλες τις σελίδες του εγγράφου PDF με τη σειρά των καρτελών;

 Α: Ναι, μπορείτε να ανακτήσετε πεδία φόρμας από όλες τις σελίδες του εγγράφου PDF κάνοντας επανάληψη σε κάθε σελίδα και πρόσβαση στο`FieldsInTabOrder` ιδιοκτησία όπως φαίνεται στο σεμινάριο. Αυτό θα σας δώσει πεδία φόρμας ταξινομημένα με βάση τη σειρά καρτελών τους σε όλες τις σελίδες.

#### Ε: Είναι δυνατή η ανάκτηση μόνο συγκεκριμένων τύπων πεδίων φόρμας, όπως πεδία κειμένου ή πλαίσια ελέγχου, με τη σειρά των καρτελών;

Α: Ναι, μπορείτε να φιλτράρετε τα πεδία φόρμας με βάση τους τύπους τους, όπως πεδία κειμένου ή πλαίσια ελέγχου, αφού τα ανακτήσετε με τη σειρά των καρτελών. Μπορείτε να χρησιμοποιήσετε προτάσεις υπό όρους για να ελέγξετε τον τύπο κάθε πεδίου φόρμας και να τις επεξεργαστείτε ανάλογα.

#### Ε: Μπορώ να ανακτήσω πεδία φόρμας με βάση τα ονόματά τους αντί για σειρά καρτελών;

 Α: Ναι, μπορείτε να ανακτήσετε πεδία φόρμας με βάση τα ονόματά τους χρησιμοποιώντας το`doc.Form` συλλογή και τον καθορισμό του ονόματος πεδίου ως ευρετηρίου. Για παράδειγμα,`doc.Form["fieldName"]`θα ανακτήσει το πεδίο φόρμας με το καθορισμένο όνομα.

#### Ε: Υποστηρίζει το Aspose.PDF για .NET την εργασία με κρυπτογραφημένα έγγραφα PDF;

Α: Ναι, το Aspose.PDF για .NET παρέχει υποστήριξη για εργασία με κρυπτογραφημένα έγγραφα PDF. Μπορείτε να φορτώσετε και να χειριστείτε κρυπτογραφημένα αρχεία PDF χρησιμοποιώντας κατάλληλες παραμέτρους κωδικού πρόσβασης.