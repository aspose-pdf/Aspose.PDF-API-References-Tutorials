---
title: Προσθήκη εσοχής επόμενων γραμμών σε αρχείο PDF
linktitle: Προσθήκη εσοχής επόμενων γραμμών σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να προσθέτετε επόμενες γραμμές εσοχή σε κείμενο σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 60
url: /el/net/programming-with-text/add-subsequent-lines-indent/
---
Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία προσθήκης επόμενων γραμμών εσοχής σε κείμενο σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα.

## Απαιτήσεις
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Visual Studio ή οποιοσδήποτε άλλος μεταγλωττιστής C# είναι εγκατεστημένος στον υπολογιστή σας.
- Aspose.PDF για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από τον επίσημο ιστότοπο του Aspose ή να χρησιμοποιήσετε έναν διαχειριστή πακέτων όπως το NuGet για να το εγκαταστήσετε.

## Βήμα 1: Ρύθμιση του έργου
1. Δημιουργήστε ένα νέο έργο C# στο περιβάλλον ανάπτυξης που προτιμάτε.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 2: Εισαγάγετε τους απαιτούμενους χώρους ονομάτων
Στο αρχείο κώδικα όπου θέλετε να προσθέσετε εσοχή επόμενων γραμμών, προσθέστε τα ακόλουθα χρησιμοποιώντας την οδηγία στο επάνω μέρος του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Βήμα 3: Ορίστε τον κατάλογο εγγράφων
 Στον κώδικα, εντοπίστε τη γραμμή που λέει`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με τη διαδρομή προς τον κατάλογο όπου είναι αποθηκευμένα τα έγγραφά σας.

## Βήμα 4: Δημιουργήστε ένα νέο αντικείμενο Document
 Δημιουργήστε ένα νέο`Document` αντικείμενο προσθέτοντας την ακόλουθη γραμμή κώδικα:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Βήμα 5: Προσθέστε μια σελίδα στο έγγραφο
 Προσθέστε μια νέα σελίδα στο έγγραφο χρησιμοποιώντας το`Add` μέθοδος του`Pages`συλλογή. Στον παρεχόμενο κωδικό, η νέα σελίδα εκχωρείται στη μεταβλητή`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Βήμα 6: Δημιουργήστε ένα TextFragment με εσοχή στις επόμενες γραμμές
 Στιγμιότυπο α`TextFragment` αντικείμενο και παρέχετε το επιθυμητό κείμενο. Στον παρεχόμενο κωδικό, το κείμενο εκχωρείται στη μεταβλητή`text` . Στη συνέχεια, αρχικοποιήστε`TextFormattingOptions` για το`TextFragment`και προσδιορίστε το`SubsequentLinesIndent` αξία.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Βήμα 7: Προσθέστε το TextFragment στη σελίδα
 Πρόσθεσε το`TextFragment` αντικείμενο στη συλλογή παραγράφων της σελίδας.

```csharp
page.Paragraphs.Add(text);
```

## Βήμα 8: Επαναλάβετε τα βήματα 6 και 7 για πρόσθετες γραμμές
Για να προσθέσετε επόμενες γραμμές με την ίδια εσοχή, επαναλάβετε τα βήματα 6 και 7 για κάθε γραμμή. Ενημερώστε το περιεχόμενο του κειμένου όπως απαιτείται.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Βήμα 9: Αποθηκεύστε το έγγραφο PDF
 Αποθηκεύστε το έγγραφο PDF χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο. Καθορίστε τη διαδρομή του αρχείου εξόδου.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Δείγμα πηγαίου κώδικα για Προσθήκη εσοχής επόμενων γραμμών χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Δημιουργία νέου αντικειμένου εγγράφου
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Εκκινήστε το TextFormattingOptions για το τμήμα κειμένου και καθορίστε την τιμή SubsequentLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## συμπέρασμα
Προσθέσατε με επιτυχία τις επόμενες γραμμές εσοχή στο κείμενο χρησιμοποιώντας το Aspose.PDF για .NET. Το αρχείο PDF που προκύπτει μπορεί τώρα να βρεθεί στην καθορισμένη διαδρομή αρχείου εξόδου.

### Συχνές ερωτήσεις

#### Ε: Ποιο είναι το επίκεντρο αυτού του σεμιναρίου;

Α: Αυτό το σεμινάριο παρέχει έναν περιεκτικό οδηγό σχετικά με τον τρόπο προσθήκης επόμενων γραμμών σε εσοχή σε κείμενο σε αρχείο PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Περιλαμβάνει παραδείγματα πηγαίου κώδικα C# για να επεξηγήσει τα βήματα που απαιτούνται για την επίτευξη αυτού του στόχου.

#### Ε: Ποιους χώρους ονομάτων πρέπει να εισαγάγω για αυτόν τον οδηγό;

Α: Στο αρχείο κώδικα όπου σκοπεύετε να προσθέσετε εσοχή επόμενων γραμμών, εισαγάγετε τους ακόλουθους χώρους ονομάτων στην αρχή του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Ε: Πώς καθορίζω τον κατάλογο εγγράφων;

 Α: Στον κωδικό, εντοπίστε τη γραμμή`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

#### Ε: Πώς μπορώ να δημιουργήσω ένα αντικείμενο Document;

 Α: Στο Βήμα 4, θα δημιουργήσετε ένα νέο`Document` αντικείμενο χρησιμοποιώντας την ακόλουθη γραμμή κώδικα:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### Ε: Πώς μπορώ να προσθέσω μια σελίδα στο έγγραφο;

 Α: Στο Βήμα 5, θα προσθέσετε μια νέα σελίδα στο έγγραφο χρησιμοποιώντας το`Add` μέθοδος του`Pages` συλλογή:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### Ε: Πώς μπορώ να προσθέσω επόμενες γραμμές εσοχή στο κείμενο;

 Α: Στο Βήμα 6, θα δημιουργήσετε ένα`TextFragment` αντικείμενο και αντιστοιχίστε σε αυτό το επιθυμητό κείμενο. Στη συνέχεια, θα αρχικοποιήσετε`TextFormattingOptions` για το`TextFragment`και προσδιορίστε το`SubsequentLinesIndent` αξία:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### Ε: Πώς μπορώ να προσθέσω το TextFragment στο έγγραφο PDF;

 Α: Στο Βήμα 7, θα προσθέσετε το`TextFragment` αντικείμενο (`text`) στη συλλογή παραγράφων της σελίδας:

```csharp
page.Paragraphs.Add(text);
```

#### Ε: Μπορώ να επαναλάβω τη διαδικασία για επιπλέον γραμμές;

 Α: Ναι, στο Βήμα 8, μπορείτε να επαναλάβετε τη διαδικασία για πρόσθετες γραμμές με την ίδια εσοχή δημιουργώντας νέα`TextFragment` αντικείμενα και προσθέτοντάς τα στη συλλογή παραγράφων της σελίδας.

#### Ε: Πώς μπορώ να αποθηκεύσω το έγγραφο PDF που προκύπτει;

 Α: Αφού προσθέσετε το κείμενο με εσοχή στις επόμενες γραμμές, χρησιμοποιήστε το`Save` μέθοδος του`Document` αντικείμενο αποθήκευσης του εγγράφου PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### Ε: Ποιο είναι το βασικό στοιχείο από αυτό το σεμινάριο;

Α: Ακολουθώντας αυτό το σεμινάριο, μάθατε με επιτυχία πώς να βελτιώσετε την αναγνωσιμότητα του κειμένου σε ένα έγγραφο PDF προσθέτοντας εσοχή στις επόμενες γραμμές χρησιμοποιώντας το Aspose.PDF για .NET. Αυτή η τεχνική μπορεί να είναι χρήσιμη για διάφορους τύπους εγγράφων και εκθέσεων.