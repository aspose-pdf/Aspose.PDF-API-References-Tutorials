---
title: Λήψη πεδίων από την περιοχή σε αρχείο PDF
linktitle: Λήψη πεδίων από την περιοχή σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Λάβετε εύκολα πεδία από μια συγκεκριμένη περιοχή σε αρχείο PDF με το Aspose.PDF για .NET.
type: docs
weight: 130
url: /el/net/programming-with-forms/get-fields-from-region/
---
Σε αυτό το σεμινάριο, θα σας δείξουμε πώς να αποκτήσετε τα πεδία μιας συγκεκριμένης περιοχής σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα C# βήμα προς βήμα για να σας καθοδηγήσουμε σε αυτήν τη διαδικασία.

## Βήμα 1: Προετοιμασία

Βεβαιωθείτε ότι έχετε εισαγάγει τις απαραίτητες βιβλιοθήκες και έχετε ορίσει τη διαδρομή προς τον κατάλογο των εγγράφων σας:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Ανοίξτε το αρχείο PDF

Ανοίξτε το αρχείο PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Βήμα 3: Δημιουργήστε ένα ορθογώνιο αντικείμενο για να δεσμεύσετε την περιοχή

Δημιουργήστε ένα ορθογώνιο αντικείμενο για να δεσμεύσετε την περιοχή όπου θέλετε να λάβετε τα πεδία:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Βήμα 4: Αποκτήστε τη φόρμα PDF

Λάβετε τη φόρμα PDF του εγγράφου:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Βήμα 5: Λάβετε τα πεδία στην ορθογώνια περιοχή

Λάβετε τα πεδία που βρίσκονται στην καθορισμένη ορθογώνια περιοχή:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Βήμα 6: Εμφάνιση ονομάτων και τιμών πεδίων

Επαναλάβετε τα πεδία που προκύπτουν και εμφανίστε τα ονόματα και τις τιμές τους:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Δείγμα πηγαίου κώδικα για Λήψη πεδίων από περιοχή χρησιμοποιώντας Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Άνοιγμα αρχείου pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Δημιουργήστε ορθογώνιο αντικείμενο για να λάβετε πεδία σε αυτήν την περιοχή
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Αποκτήστε τη φόρμα PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Λάβετε πεδία στην ορθογώνια περιοχή
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Εμφάνιση ονομάτων και τιμών πεδίων
foreach (Field field in fields)
{
	// Εμφάνιση ιδιοτήτων τοποθέτησης εικόνας για όλες τις τοποθετήσεις
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να λαμβάνουμε τα πεδία μιας συγκεκριμένης περιοχής σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να εξαγάγετε τα πεδία που βρίσκονται σε μια δεδομένη ορθογώνια περιοχή του εγγράφου PDF σας χρησιμοποιώντας το Aspose.PDF.

### Συχνές ερωτήσεις

#### Ε: Μπορώ να χρησιμοποιήσω αυτήν τη μέθοδο για να λάβω πεδία από μια μη ορθογώνια περιοχή σε ένα έγγραφο PDF;

 Α: Όχι, η παρεχόμενη μέθοδος`GetFieldsInRect` έχει σχεδιαστεί ειδικά για την ανάκτηση πεδίων που βρίσκονται σε μια ορθογώνια περιοχή σε ένα έγγραφο PDF. Εάν χρειάζεται να εξαγάγετε πεδία από μια μη ορθογώνια περιοχή, θα πρέπει να εφαρμόσετε προσαρμοσμένη λογική για να προσδιορίσετε και να εξαγάγετε τα πεδία με βάση άλλα κριτήρια, όπως συντεταγμένες πεδίων ή ονόματα.

#### Ε: Πώς μπορώ να τροποποιήσω το μέγεθος ή τη θέση του ορθογωνίου για να λάβω πεδία από διαφορετική περιοχή;

 Α: Για να λάβετε πεδία από διαφορετική περιοχή, μπορείτε να τροποποιήσετε το`Aspose.Pdf.Rectangle` οι παράμετροι του αντικειμένου που χρησιμοποιούνται για τον ορισμό του οριοθετημένου ορθογωνίου. ο`Rectangle` Ο κατασκευαστής παίρνει τέσσερις παραμέτρους:`x`, `y`, `width` , και`height`που αντιπροσωπεύουν τις συντεταγμένες πάνω-αριστερής γωνίας και τις διαστάσεις του ορθογωνίου. Η προσαρμογή αυτών των παραμέτρων θα αλλάξει την περιοχή από την οποία εξάγονται τα πεδία.

#### Ε: Τι γίνεται αν δεν υπάρχουν πεδία εντός της καθορισμένης ορθογώνιας περιοχής;

 Α: Εάν δεν υπάρχουν πεδία εντός της καθορισμένης ορθογώνιας περιοχής, το`GetFieldsInRect` μέθοδος θα επιστρέψει έναν κενό πίνακα. Μπορείτε να ελέγξετε το μήκος του πίνακα για να προσδιορίσετε εάν υπάρχουν πεδία εντός της περιοχής.

#### Ε: Μπορώ να λάβω πεδία από επικαλυπτόμενες περιοχές σε ένα έγγραφο PDF;

 Α: Ναι, μπορείτε να λάβετε πεδία από επικαλυπτόμενες περιοχές σε ένα έγγραφο PDF δημιουργώντας πολλά`Aspose.Pdf.Rectangle` αντικείμενα και καλώντας το`GetFieldsInRect` μέθοδο για καθένα από αυτά. Ο χειρισμός των επικαλυπτόμενων περιοχών θα γίνεται ανεξάρτητα και θα λαμβάνετε ξεχωριστούς πίνακες πεδίων για κάθε περιοχή.

#### Ε: Είναι δυνατή η λήψη πεδίων από μια συγκεκριμένη σελίδα ή πολλές σελίδες στο έγγραφο PDF;

Α: Ναι, μπορείτε να λάβετε πεδία από μια συγκεκριμένη σελίδα ή πολλές σελίδες σε ένα έγγραφο PDF. Για να το πετύχετε αυτό, μπορείτε να φορτώσετε το έγγραφο PDF, να αποκτήσετε πρόσβαση στις επιθυμητές σελίδες χρησιμοποιώντας το`doc.Pages` συλλογή και, στη συνέχεια, εφαρμόστε το`GetFieldsInRect` μέθοδος για τη συγκεκριμένη περιοχή κάθε σελίδας.