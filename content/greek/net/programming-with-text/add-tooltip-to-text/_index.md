---
title: Προσθήκη επεξήγησης εργαλείου σε κείμενο σε αρχείο PDF
linktitle: Προσθήκη επεξήγησης εργαλείου σε κείμενο σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να προσθέτετε συμβουλές εργαλείων σε κείμενο σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 90
url: /el/net/programming-with-text/add-tooltip-to-text/
---
Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία προσθήκης συμβουλών εργαλείων σε κείμενο σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα.

## Απαιτήσεις
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Visual Studio ή οποιοσδήποτε άλλος μεταγλωττιστής C# είναι εγκατεστημένος στον υπολογιστή σας.
- Aspose.PDF για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από τον επίσημο ιστότοπο του Aspose ή να χρησιμοποιήσετε έναν διαχειριστή πακέτων όπως το NuGet για να το εγκαταστήσετε.

## Βήμα 1: Ρύθμιση του έργου
1. Δημιουργήστε ένα νέο έργο C# στο περιβάλλον ανάπτυξης που προτιμάτε.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 2: Εισαγάγετε τους απαιτούμενους χώρους ονομάτων
Στο αρχείο κώδικα όπου θέλετε να προσθέσετε συμβουλές εργαλείων στο κείμενο, προσθέστε τα ακόλουθα χρησιμοποιώντας οδηγίες στο επάνω μέρος του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Βήμα 3: Ορίστε τον κατάλογο εγγράφων
 Στον κώδικα, εντοπίστε τη γραμμή που λέει`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με τη διαδρομή προς τον κατάλογο όπου είναι αποθηκευμένα τα έγγραφά σας.

## Βήμα 4: Δημιουργήστε ένα δείγμα εγγράφου με κείμενο
 Δημιουργήστε ένα νέο`Document`αντικείμενο και προσθήκη σελίδων με θραύσματα κειμένου. Στον παρεχόμενο κώδικα, δύο τμήματα κειμένου προστίθενται στο έγγραφο με το αντίστοιχο κείμενο συμβουλής εργαλείου.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Βήμα 5: Ανοίξτε το έγγραφο και βρείτε τα τμήματα κειμένου
 Φορτώστε το έγγραφο που δημιουργήθηκε χρησιμοποιώντας το`Document` κατασκευαστή και βρείτε τα τμήματα κειμένου που χρειάζονται συμβουλές εργαλείων χρησιμοποιώντας`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Βήμα 6: Προσθέστε συμβουλές εργαλείων στα τμήματα κειμένου
 Κάντε βρόχο μέσα από τα εξαγόμενα τμήματα κειμένου και δημιουργήστε αόρατα κουμπιά στις θέσεις τους. Αντιστοιχίστε το επιθυμητό κείμενο συμβουλής εργαλείου στο`AlternateName` ιδιοκτησία του`ButtonField`. Προσθέστε τα πεδία του κουμπιού στη φόρμα του εγγράφου.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Βήμα 7: Επαναλάβετε για πρόσθετα τμήματα κειμένου με μεγάλες συμβουλές εργαλείων
Επαναλάβετε τα βήματα 5 και 6 για αποσπάσματα κειμένου με μεγάλες συμβουλές εργαλείων. Τροποποιήστε ανάλογα τα κριτήρια αναζήτησης και το κείμενο συμβουλής εργαλείου.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Βήμα 8: Αποθηκεύστε το τροποποιημένο έγγραφο
 Αποθηκεύστε το τροποποιημένο έγγραφο PDF χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
document. Save(outputFile);
```

### Δείγμα πηγαίου κώδικα για Προσθήκη επεξήγησης εργαλείου σε κείμενο χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Δημιουργία δείγματος εγγράφου με κείμενο
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Άνοιγμα εγγράφου με κείμενο
Document document = new Document(outputFile);
//Δημιουργήστε αντικείμενο TextAbsorber για να βρείτε όλες τις φράσεις που ταιριάζουν με την κανονική έκφραση
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Αποδεχτείτε τον απορροφητήρα για τις σελίδες του εγγράφου
document.Pages.Accept(absorber);
// Λάβετε τα εξαγόμενα τμήματα κειμένου
TextFragmentCollection textFragments = absorber.TextFragments;
// Περιηγηθείτε στα θραύσματα
foreach (TextFragment fragment in textFragments)
{
	// Δημιουργία αόρατου κουμπιού στη θέση του τμήματος κειμένου
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Η τιμή AlternateName θα εμφανίζεται ως επεξήγηση εργαλείου από μια εφαρμογή προβολής
	field.AlternateName = "Tooltip for text.";
	// Προσθήκη πεδίου κουμπιού στο έγγραφο
	document.Form.Add(field);
}
// Στη συνέχεια θα είναι ένα δείγμα από πολύ μακριά επεξήγηση εργαλείου
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Ορίστε πολύ μεγάλο κείμενο
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Αποθήκευση εγγράφου
document.Save(outputFile);
```

## Σύναψη
Προσθέσατε με επιτυχία συμβουλές εργαλείων σε κείμενο σε έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Το αρχείο PDF που προκύπτει μπορεί τώρα να βρεθεί στην καθορισμένη διαδρομή αρχείου εξόδου.

## Συχνές ερωτήσεις

#### Ε: Ποιο είναι το επίκεντρο αυτού του σεμιναρίου;

Α: Αυτό το σεμινάριο εστιάζει στην προσθήκη συμβουλών εργαλείων σε κείμενο μέσα σε ένα αρχείο PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα βήματα που απαιτούνται για να επιτευχθεί αυτό.

#### Ε: Ποιοι χώροι ονομάτων πρέπει να εισαχθούν για αυτόν τον οδηγό;

Α: Στο αρχείο κώδικα όπου θέλετε να προσθέσετε συμβουλές εργαλείων στο κείμενο, εισαγάγετε τους ακόλουθους χώρους ονομάτων στην αρχή του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### Ε: Πώς καθορίζω τον κατάλογο εγγράφων;

 Α: Στον κώδικα, βρείτε τη γραμμή`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

#### Ε: Πώς μπορώ να δημιουργήσω ένα δείγμα εγγράφου με κείμενο;

 Α: Στο Βήμα 4, θα δημιουργήσετε ένα νέο`Document` αντικείμενο και προσθήκη σελίδων με θραύσματα κειμένου. Ο παρεχόμενος κώδικας προσθέτει δύο τμήματα κειμένου με το αντίστοιχο κείμενο συμβουλής εργαλείου.

#### Ε: Πώς μπορώ να ανοίξω το έγγραφο και να βρω τα τμήματα κειμένου;

 Α: Στο Βήμα 5, θα φορτώσετε το έγγραφο που δημιουργήθηκε χρησιμοποιώντας το`Document` κατασκευαστή και βρείτε τα τμήματα κειμένου που απαιτούν συμβουλές εργαλείων χρησιμοποιώντας το`TextFragmentAbsorber`.

#### Ε: Πώς μπορώ να προσθέσω συμβουλές εργαλείων στα τμήματα κειμένου;

 Α: Στο Βήμα 6, θα κάνετε κύκλο στα τμήματα κειμένου που έχουν εξαχθεί και θα δημιουργήσετε αόρατα κουμπιά στις θέσεις τους. Το κείμενο συμβουλής εργαλείου εκχωρείται στο`AlternateName` ιδιοκτησία του`ButtonField`, το οποίο προστίθεται στη φόρμα του εγγράφου.

#### Ε: Πώς μπορώ να επαναλάβω τη διαδικασία για πρόσθετα τμήματα κειμένου με μεγάλες συμβουλές εργαλείων;

Α: Για θραύσματα κειμένου με μεγάλες επεξηγήσεις εργαλείων, επαναλάβετε τα βήματα 5 και 6. Τροποποιήστε τα κριτήρια αναζήτησης και το κείμενο της συμβουλής εργαλείου ανάλογα.

#### Ε: Πώς μπορώ να αποθηκεύσω το τροποποιημένο έγγραφο;

 Α: Στο Βήμα 8, θα αποθηκεύσετε το τροποποιημένο έγγραφο PDF χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

#### Ε: Ποιο είναι το κύριο στοιχείο από αυτό το σεμινάριο;

Α: Ακολουθώντας αυτό το σεμινάριο, μάθατε πώς να βελτιώσετε το έγγραφο PDF προσθέτοντας συμβουλές εργαλείων στο κείμενο χρησιμοποιώντας το Aspose.PDF για .NET. Αυτό μπορεί να παρέχει πολύτιμες πρόσθετες πληροφορίες στους αναγνώστες όταν αλληλεπιδρούν με το περιεχόμενο PDF.