---
title: Προσθήκη Αφαίρεση Javascript σε έγγραφο PDF
linktitle: Προσθήκη Αφαίρεση Javascript στο Έγγραφο
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να προσθέτετε και να αφαιρείτε JavaScript σε έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Οδηγός βήμα προς βήμα με σεμινάρια κώδικα για δέσμες ενεργειών σε επίπεδο εγγράφου.
type: docs
weight: 30
url: /el/net/programming-with-document/addremovejavascripttodoc/
---
Για να προσθέσουμε και να αφαιρέσουμε JavaScript σε έγγραφο PDF, θα χρησιμοποιήσουμε τη βιβλιοθήκη Aspose.PDF για .NET. Αυτή η ισχυρή βιβλιοθήκη μας επιτρέπει να χειριζόμαστε αρχεία PDF σε εφαρμογές .NET. Ακολουθήστε τις παρακάτω οδηγίες βήμα προς βήμα για να προσθέσετε και να αφαιρέσετε JavaScript χρησιμοποιώντας το Aspose.PDF για .NET.

## Βήμα 1: Δημιουργήστε ένα νέο έγγραφο PDF

 Ξεκινήστε δημιουργώντας μια νέα παρουσία του`Document` κλάση που παρέχεται από το Aspose.PDF για .NET. Αυτό θα χρησιμεύσει ως το έγγραφο PDF όπου θα προσθέσουμε το JavaScript.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Βήμα 2: Προσθέστε JavaScript σε επίπεδο εγγράφου

 Για να προσθέσετε JavaScript σε επίπεδο εγγράφου, χρησιμοποιήστε το`JavaScript` ιδιοκτησία του`Document` τάξη. Εκχωρήστε λειτουργίες JavaScript σε κλειδιά στο λεξικό JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 Σε αυτό το σεμινάριο, έχουμε προσθέσει δύο λειτουργίες JavaScript,`func1` και`func2`, στο έγγραφο PDF.

## Βήμα 3: Κατάργηση JavaScript σε επίπεδο εγγράφου

 Για να καταργήσετε τη JavaScript σε επίπεδο εγγράφου, φορτώστε το έγγραφο PDF και αποκτήστε πρόσβαση σε αυτό`JavaScript`λεξικό. Επαναλάβετε τα πλήκτρα και αφαιρέστε την επιθυμητή συνάρτηση JavaScript.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 Σε αυτό το σεμινάριο, αφαιρούμε το`func1` Λειτουργία JavaScript από το έγγραφο PDF.

## Βήμα 4: Αποθήκευση και επαλήθευση αλλαγών

Αποθηκεύστε το τροποποιημένο έγγραφο PDF και επαληθεύστε τις αλλαγές.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Αυτός ο κωδικός θα αποθηκεύσει το τροποποιημένο έγγραφο PDF και θα εμφανίσει το μήνυμα επιτυχίας.

### Παράδειγμα πηγαίου κώδικα για Προσθήκη Αφαίρεση Javascript από έγγραφα PDF χρησιμοποιώντας Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Κατάργηση JavaScript σε επίπεδο εγγράφου
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## συμπέρασμα

Σε αυτό το άρθρο, παρέχουμε έναν οδηγό βήμα προς βήμα για την προσθήκη και την αφαίρεση JavaScript από έγγραφα PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας τις οδηγίες και χρησιμοποιώντας τα παρεχόμενα σεμινάρια κώδικα, μπορείτε εύκολα να ενσωματώσετε JavaScript στα έγγραφά σας PDF και να το αφαιρέσετε όταν χρειάζεται. Η JavaScript επιτρέπει τη δυναμική λειτουργικότητα και τη διαδραστικότητα στα αρχεία PDF σας, βελτιώνοντας την εμπειρία χρήστη.


### Συχνές ερωτήσεις για την προσθήκη αφαίρεσης javascript σε έγγραφο PDF

#### Ε: Τι είναι το Aspose.PDF για .NET;

Α: Το Aspose.PDF για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να χειρίζονται αποτελεσματικά αρχεία PDF σε εφαρμογές .NET. Παρέχει εκτεταμένες δυνατότητες για εργασία με έγγραφα PDF μέσω προγραμματισμού.

#### Ε: Πώς μπορώ να προσθέσω JavaScript σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET;

 Α: Μπορείτε να προσθέσετε JavaScript σε επίπεδο εγγράφου χρησιμοποιώντας το`JavaScript` ιδιοκτησία του`Document` τάξη. Απλώς αντιστοιχίστε λειτουργίες JavaScript σε κλειδιά στο λεξικό JavaScript.

#### Ε: Μπορώ να αφαιρέσω το JavaScript από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET;

 Α: Ναι, μπορείτε να καταργήσετε τη JavaScript από ένα έγγραφο PDF μεταβαίνοντας στο`JavaScript` λεξικό και αφαιρώντας την επιθυμητή λειτουργία JavaScript.

#### Ε: Είναι το Aspose.PDF για .NET κατάλληλο για επαγγελματικά έργα;

Α: Απολύτως, το Aspose.PDF για .NET χρησιμοποιείται ευρέως σε επαγγελματικά έργα για εργασίες χειρισμού PDF και δημιουργίας. Προσφέρει υψηλή απόδοση και αξιόπιστη λειτουργικότητα.

#### Ε: Ποια οφέλη παρέχει η προσθήκη JavaScript σε ένα έγγραφο PDF;

Α: Η προσθήκη JavaScript σε ένα έγγραφο PDF σάς δίνει τη δυνατότητα να δημιουργήσετε διαδραστικά και δυναμικά αρχεία PDF. Μπορείτε να εφαρμόσετε επικύρωση φόρμας, να εκτελέσετε υπολογισμούς και να προσθέσετε διάφορες λειτουργίες διαδραστικότητας για να βελτιώσετε την εμπειρία χρήστη.