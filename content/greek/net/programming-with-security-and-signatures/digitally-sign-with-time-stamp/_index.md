---
title: Ψηφιακή υπογραφή με χρονική σφραγίδα σε αρχείο PDF
linktitle: Ψηφιακή υπογραφή με χρονική σφραγίδα σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να υπογράφετε ψηφιακά ένα PDF με χρονική σήμανση χρησιμοποιώντας το Aspose.PDF για .NET. Αυτός ο οδηγός βήμα προς βήμα καλύπτει προαπαιτούμενα, ρύθμιση πιστοποιητικού, χρονοσήμανση και πολλά άλλα.
type: docs
weight: 50
url: /el/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Εισαγωγή

Χρειάστηκε ποτέ να υπογράψετε ψηφιακά ένα PDF και να συμπεριλάβετε μια χρονική σήμανση για επιπλέον ασφάλεια; Είτε εργάζεστε σε νομικά έγγραφα, συμβόλαια ή οτιδήποτε απαιτεί ασφαλή έλεγχο ταυτότητας, μια ψηφιακή υπογραφή με χρονική σήμανση προσθέτει ένα επιπλέον επίπεδο αξιοπιστίας. Σε αυτό το σεμινάριο, θα αναλύσουμε πώς μπορείτε να χρησιμοποιήσετε το Aspose.PDF για .NET για να προσθέσετε μια ψηφιακή υπογραφή μαζί με μια χρονική σήμανση στα έγγραφά σας PDF. Μην ανησυχείτε, θα το κάνουμε βήμα βήμα!

## Προαπαιτούμενα

Πριν βουτήξουμε στον κώδικα, υπάρχουν μερικά πράγματα που θα πρέπει να ρυθμίσετε για να ακολουθήσετε. Ακολουθεί μια γρήγορη λίστα ελέγχου των προϋποθέσεων για να ξεκινήσετε:

-  Aspose.PDF για Βιβλιοθήκη .NET: Θα χρειαστείτε τη βιβλιοθήκη Aspose.PDF για .NET εγκατεστημένη στο έργο σας. Μπορείτε[κατεβάστε την τελευταία έκδοση εδώ](https://releases.aspose.com/pdf/net/) ή προσθέστε το στο έργο σας μέσω του NuGet.
- Ένα έγγραφο PDF: Θα χρειαστείτε ένα δείγμα αρχείου PDF για να εργαστείτε. Βεβαιωθείτε ότι έχετε ένα αρχείο στον κατάλογο του έργου σας που θέλετε να υπογράψετε.
-  Ψηφιακό πιστοποιητικό (αρχείο PFX): Βεβαιωθείτε ότι διαθέτετε ψηφιακό πιστοποιητικό (α`.pfx` αρχείο) για την ψηφιακή υπογραφή του εγγράφου.
- Χρονική σήμανση URL: Πρόκειται για μια διαδικτυακή υπηρεσία χρονοσήμανσης που θα χρησιμοποιηθεί για την επισύναψη χρονικής σφραγίδας στην ψηφιακή υπογραφή. 
- Βασικές γνώσεις C#: Δεν χρειάζεται να είστε ειδικός, αλλά η γνώση των βασικών στοιχείων της C# θα σας βοηθήσει να κατανοήσετε και να προσαρμόσετε τον κώδικα.

Αφού σημειώσετε όλα αυτά τα πλαίσια, είστε έτοιμοι να ξεκινήσετε την κωδικοποίηση!

## Εισαγωγή πακέτων

Για να ξεκινήσετε, θα χρειαστεί να εισαγάγετε τους παρακάτω χώρους ονομάτων στο έργο σας C#. Αυτό διασφαλίζει ότι έχετε πρόσβαση στις σχετικές κλάσεις και συναρτήσεις Aspose.PDF.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Βήμα 1: Φορτώστε το έγγραφο PDF

Το πρώτο πράγμα που πρέπει να κάνουμε είναι να φορτώσουμε το έγγραφο PDF που θέλουμε να υπογράψουμε. Δείτε πώς το κάνετε αυτό:

```csharp
// Καθορίστε τη διαδρομή προς τον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Φορτώστε το έγγραφο PDF
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Αυτό το βήμα είναι αρκετά απλό. Απλώς ορίζουμε τη διαδρομή προς το έγγραφο που θέλουμε να υπογράψουμε. Ο`Document` class από το Aspose.PDF χειρίζεται τη φόρτωση του αρχείου.

## Βήμα 2: Ρυθμίστε την ψηφιακή υπογραφή

Στη συνέχεια, θα δημιουργήσουμε την ψηφιακή υπογραφή χρησιμοποιώντας την κλάση PKCS7 και θα φορτώσουμε το αρχείο PFX. Αυτό το αρχείο PFX περιέχει το πιστοποιητικό και το ιδιωτικό κλειδί σας, τα οποία είναι απαραίτητα για την υπογραφή του εγγράφου.

```csharp
// Διαδρομή προς το αρχείο .pfx
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Αρχικοποιήστε το αντικείμενο υπογραφής
PdfFileSignature signature = new PdfFileSignature(document);

// Φορτώστε το αρχείο PFX με κωδικό πρόσβασης
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 Σε αυτό το σημείο, λέτε στην Aspose να χρησιμοποιήσει το ψηφιακό πιστοποιητικό σας για την υπογραφή του εγγράφου. Ο`PKCS7`Το αντικείμενο χειρίζεται όλη την κρυπτογραφική εργασία για εσάς, έτσι δεν χρειάζεται να ανησυχείτε για τις λεπτές λεπτομέρειες.

## Βήμα 3: Προσθέστε τις Ρυθμίσεις χρονοσήμανσης

Ένα από τα βασικά στοιχεία μιας ισχυρής ψηφιακής υπογραφής είναι η χρονική σήμανση. Αυτό διασφαλίζει ότι η υπογραφή του εγγράφου μπορεί να επαληθευτεί ακόμη και μετά τη λήξη του πιστοποιητικού. Ας ρυθμίσουμε τη χρονική σήμανση χρησιμοποιώντας μια ηλεκτρονική αρχή χρονοσήμανσης.

```csharp
// Καθορίστε τις ρυθμίσεις χρονικής σήμανσης
TimestampSettings timestampSettings = new TimestampSettings("https://your_timestamp_url", "user:password");

// Προσθέστε ρυθμίσεις χρονικής σφραγίδας στο αντικείμενο PKCS7
pkcs.TimestampSettings = timestampSettings;
```

Εδώ, καθορίζετε τη διεύθυνση URL για την υπηρεσία χρονοσήμανσης, η οποία θα παρέχει αυτόματα ώρα και ημερομηνία στην υπογραφή σας. Αυτό μπορεί να γίνει με ή χωρίς έλεγχο ταυτότητας.

## Βήμα 4: Καθορίστε τη θέση και την εμφάνιση της υπογραφής

Τώρα, θα ορίσουμε πού θα εμφανίζεται η υπογραφή στο PDF και τις διαστάσεις της. Μπορείτε να προσαρμόσετε τη θέση του πλαισίου υπογραφής στη σελίδα, καθώς και το μέγεθος.

```csharp
//Καθορίστε την εμφάνιση και τη θέση της υπογραφής (σελίδα 1, με καθορισμένο ορθογώνιο)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Εδώ, ορίζουμε ένα ορθογώνιο που τοποθετεί την υπογραφή στις συντεταγμένες (100, 100) στην πρώτη σελίδα του PDF, με πλάτος 200 και ύψος 100. Μπορείτε να αλλάξετε αυτές τις τιμές για να ταιριάζουν στο σχέδιό σας.

## Βήμα 5: Υπογράψτε το έγγραφο PDF

Με όλα τα ρυθμισμένα, ήρθε η ώρα να εφαρμόσετε πραγματικά την ψηφιακή υπογραφή στο PDF. Αυτό το βήμα συνδυάζει το πιστοποιητικό, τη χρονική σήμανση και την τοποθέτηση σε μια απλή εντολή.

```csharp
// Υπογράψτε το έγγραφο στην πρώτη σελίδα
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Να τι συμβαίνει:
- 1: Αυτό υποδηλώνει ότι η υπογραφή πρέπει να εφαρμοστεί στην πρώτη σελίδα.
- "Υπογραφή Αιτία": Εδώ μπορείτε να καθορίσετε γιατί υπογράφετε το έγγραφο.
- "Επικοινωνία": Εισαγάγετε τα στοιχεία επικοινωνίας του υπογράφοντος.
- "Τοποθεσία": Καθορίστε τη θέση του υπογράφοντος.
- true: Αυτή η boolean τιμή υποδεικνύει εάν η υπογραφή είναι ορατή στο έγγραφο.
- rect: Το ορθογώνιο που ορίσαμε νωρίτερα καθορίζει το μέγεθος και τη θέση της υπογραφής.
- pkcs: Το αντικείμενο PKCS7 περιέχει το ψηφιακό πιστοποιητικό και τις ρυθμίσεις χρονικής σφραγίδας.

## Βήμα 6: Αποθηκεύστε το υπογεγραμμένο PDF

Μόλις υπογραφεί το έγγραφο, το μόνο που απομένει είναι να το αποθηκεύσετε. Μπορείτε να επιλέξετε ένα νέο όνομα αρχείου για να διατηρήσετε τόσο την αρχική όσο και την υπογεγραμμένη έκδοση.

```csharp
// Αποθηκεύστε το υπογεγραμμένο έγγραφο PDF
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

Το πρόσφατα υπογεγραμμένο και χρονοσήμανση PDF σας αποθηκεύεται τώρα στον καθορισμένο κατάλογο!

## Σύναψη

Και ορίστε το! Έχετε υπογράψει επιτυχώς ψηφιακά ένα PDF με χρονική σήμανση χρησιμοποιώντας το Aspose.PDF για .NET. Αυτή η διαδικασία διασφαλίζει τη γνησιότητα και την ακεραιότητα των εγγράφων σας, παρέχοντας τόσο σε εσάς όσο και στον παραλήπτη ηρεμία. Οι ψηφιακές υπογραφές γίνονται ολοένα και πιο απαραίτητες στον σημερινό ψηφιακό κόσμο, επομένως η γνώση αυτής της διαδικασίας είναι σίγουρα μια δεξιότητα που αξίζει να έχετε.

## Συχνές ερωτήσεις

### Μπορώ να χρησιμοποιήσω διαφορετική μορφή αρχείου για το πιστοποιητικό;  
Ναι, αλλά το σεμινάριο εστιάζει στη χρήση ενός αρχείου PFX, το οποίο είναι η πιο κοινή μορφή για ψηφιακά πιστοποιητικά.

### Χρειάζομαι σύνδεση στο διαδίκτυο για να εφαρμόσω τη χρονική σήμανση;  
Ναι, καθώς η χρονική σήμανση έχει ληφθεί από μια ηλεκτρονική αρχή χρονοσήμανσης, θα χρειαστείτε πρόσβαση στο Διαδίκτυο.

### Μπορώ να υπογράψω πολλές σελίδες σε ένα PDF;  
 Απολύτως! Μπορείτε να τροποποιήσετε το`signature.Sign()` μέθοδος στόχευσης πολλαπλών σελίδων ή επαναφοράς σε όλες τις σελίδες.

### Τι συμβαίνει εάν ο κωδικός πρόσβασης του αρχείου PFX είναι εσφαλμένος;  
Θα λάβετε εξαίρεση εάν ο κωδικός πρόσβασης είναι λάθος, επομένως βεβαιωθείτε ότι έχει εισαχθεί σωστά.

### Μπορώ να κάνω την υπογραφή αόρατη;  
 Ναι, μπορείς να περάσεις`false` στο`Sign` την παράμετρο ορατότητας της μεθόδου για να γίνει η υπογραφή αόρατη.