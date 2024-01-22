---
title: Προσθήκη Java Script σε αρχείο PDF
linktitle: Προσθήκη αρχείου PDF Script Java
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς μπορείτε να προσθέσετε JavaScript σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Οδηγός βήμα προς βήμα με σεμινάρια κώδικα για δέσμες ενεργειών σε επίπεδο εγγράφων και σελίδας.
type: docs
weight: 10
url: /el/net/programming-with-document/addjavascripttopage/
---
Για να προσθέσουμε JavaScript σε ένα αρχείο PDF, θα χρησιμοποιήσουμε το Aspose.PDF για .NET. Αυτή η βιβλιοθήκη παρέχει έναν απλό και αποτελεσματικό τρόπο εργασίας με αρχεία PDF σε εφαρμογές .NET. Τα παρακάτω βήματα θα σας καθοδηγήσουν στη διαδικασία προσθήκης JavaScript σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.

## Βήμα 1: Φορτώστε το αρχείο PDF

 Το πρώτο βήμα είναι να φορτώσετε το αρχείο PDF στο οποίο θέλετε να προσθέσετε JavaScript. Μπορείτε να το κάνετε αυτό χρησιμοποιώντας το`Document` κλάση που παρέχεται από το Aspose.PDF για .NET. ο`Document` class παρέχει μεθόδους φόρτωσης, αποθήκευσης και χειρισμού αρχείων PDF.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Φορτώστε ένα υπάρχον αρχείο PDF
Document doc = new Document(dataDir + "input.pdf");
```

## Βήμα 2: Προσθέστε JavaScript σε επίπεδο εγγράφου

Για να προσθέσουμε JavaScript σε επίπεδο εγγράφου, θα χρησιμοποιήσουμε το`JavascriptAction` κλάση που παρέχεται από το Aspose.PDF για .NET. Αυτή η κλάση σάς επιτρέπει να καθορίσετε τη δήλωση JavaScript που θέλετε να προσθέσετε στο αρχείο PDF.

```csharp
// Προσθήκη JavaScript σε επίπεδο εγγράφου
// Δημιουργήστε Instant JavascriptAction με την επιθυμητή δήλωση JavaScript
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Αντιστοιχίστε το αντικείμενο JavascriptAction στην επιθυμητή ενέργεια του Document
doc.OpenAction = javaScript;
```

Σε αυτό το σεμινάριο, προσθέτουμε μια δήλωση JavaScript που θα εκτυπώσει το αρχείο PDF με τις καθορισμένες επιλογές όταν ανοίξει το έγγραφο.

## Βήμα 3: Προσθήκη JavaScript σε επίπεδο σελίδας

 Για να προσθέσουμε JavaScript σε επίπεδο σελίδας, θα χρησιμοποιήσουμε το`JavascriptAction` τάξη και το`Actions` ιδιοκτησία που παρέχεται από το Aspose.PDF για .NET. Αυτή η ιδιότητα σάς επιτρέπει να καθορίσετε δηλώσεις JavaScript που θα εκτελούνται όταν ανοίξει ή κλείσει η σελίδα.

```csharp
// Προσθήκη JavaScript σε επίπεδο σελίδας
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

Σε αυτό το σεμινάριο, προσθέτουμε δηλώσεις JavaScript που θα εμφανίζουν ένα μήνυμα ειδοποίησης όταν ανοίξει ή κλείσει η σελίδα.

## Βήμα 4: Αποθηκεύστε το αρχείο PDF

Αφού προσθέσετε το JavaScript στο αρχείο PDF, πρέπει να αποθηκεύσετε το τροποποιημένο αρχείο. Μπορείτε να το κάνετε αυτό χρησιμοποιώντας το`Save` μέθοδο που παρέχεται από το`Document` τάξη.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Αποθήκευση εγγράφου PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Αυτός ο κώδικας θα αποθηκεύσει το τροποποιημένο αρχείο PDF στον καθορισμένο κατάλογο.

### Παράδειγμα πηγαίου κώδικα για Προσθήκη Java Script στη σελίδα χρησιμοποιώντας Aspose.PDF για .NET

```csharp
            
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Φορτώστε ένα υπάρχον αρχείο PDF
Document doc = new Document(dataDir + "input.pdf");

// Προσθήκη JavaScript σε επίπεδο εγγράφου
// Δημιουργήστε το JavascriptAction με την επιθυμητή δήλωση JavaScript
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Αντιστοιχίστε το αντικείμενο JavascriptAction στην επιθυμητή ενέργεια του Document
doc.OpenAction = javaScript;

// Προσθήκη JavaScript σε επίπεδο σελίδας
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Αποθήκευση εγγράφου PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## συμπέρασμα

Σε αυτό το άρθρο, εξηγήσαμε πώς να προσθέσετε JavaScript σε ένα αρχείο PDF τόσο σε επίπεδο εγγράφου όσο και σε επίπεδο σελίδας χρησιμοποιώντας το Aspose.PDF για .NET. Παρέχουμε οδηγίες βήμα προς βήμα και συμπεριλάβαμε τον πλήρη πηγαίο κώδικα για κάθε παράδειγμα. Με αυτή τη γνώση, μπορείτε να προσθέσετε JavaScript στα αρχεία PDF σας και να προσαρμόσετε τη συμπεριφορά τους σύμφωνα με τις ανάγκες σας.


### Συχνές ερωτήσεις για την προσθήκη script java σε αρχείο PDF

#### Ε: Τι είναι το Aspose.PDF για .NET;

Α: Το Aspose.PDF για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται με αρχεία PDF σε εφαρμογές .NET. Παρέχει ένα ευρύ φάσμα δυνατοτήτων για τη δημιουργία, τροποποίηση και χειρισμό εγγράφων PDF.

#### Ε: Μπορώ να προσθέσω JavaScript σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Ναι, το Aspose.PDF για .NET σάς επιτρέπει να προσθέσετε JavaScript τόσο στο επίπεδο εγγράφου όσο και στο επίπεδο σελίδας ενός αρχείου PDF, δίνοντάς σας τη δυνατότητα να δημιουργήσετε δυναμικά και διαδραστικά έγγραφα PDF.

#### Ε: Πώς μπορώ να φορτώσω ένα υπάρχον αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET;

 Α: Μπορείτε να φορτώσετε ένα υπάρχον αρχείο PDF χρησιμοποιώντας το`Document` κλάση και τις μεθόδους της, όπως φαίνεται στον οδηγό βήμα προς βήμα.

#### Ε: Τι τύπους ενεργειών JavaScript μπορώ να προσθέσω σε ένα έγγραφο PDF;

Α: Με το Aspose.PDF για .NET, μπορείτε να προσθέσετε μια μεγάλη ποικιλία ενεργειών JavaScript, όπως εκτύπωση, μηνύματα ειδοποίησης, χειραγώγηση πεδίου φόρμας και άλλα.

#### Ε: Είναι το Aspose.PDF για .NET κατάλληλο για εμπορικά έργα;

Α: Ναι, το Aspose.PDF για .NET είναι μια αξιόπιστη και ισχυρή βιβλιοθήκη που χρησιμοποιείται συνήθως σε εμπορικά έργα για εργασίες χειρισμού PDF και δημιουργίας.

