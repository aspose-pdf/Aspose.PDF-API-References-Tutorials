---
title: Αναζήτηση κειμένου και προσθήκη υπερσυνδέσμου
linktitle: Αναζήτηση κειμένου και προσθήκη υπερσυνδέσμου
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να αναζητάτε κείμενο σε ένα PDF, να προσθέτετε υπερσυνδέσμους στο κείμενο που βρέθηκε και να αποθηκεύετε το τροποποιημένο έγγραφο χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 450
url: /el/net/programming-with-text/search-text-and-add-hyperlink/
---
Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.PDF για .NET για να αναζητήσετε συγκεκριμένο κείμενο σε ένα έγγραφο PDF, να προσθέσετε μια υπερ-σύνδεση στο κείμενο που βρέθηκε και να αποθηκεύσετε το τροποποιημένο έγγραφο. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τη διαδικασία βήμα προς βήμα.

## Προαπαιτούμενα

Πριν συνεχίσετε με το σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:

- Βασικές γνώσεις γλώσσας προγραμματισμού C#.
- Εγκαταστάθηκε το Aspose.PDF για τη βιβλιοθήκη .NET. Μπορείτε να το αποκτήσετε από τον ιστότοπο Aspose ή να χρησιμοποιήσετε το NuGet για να το εγκαταστήσετε στο έργο σας.

## Βήμα 1: Ρύθμιση του έργου

Ξεκινήστε δημιουργώντας ένα νέο έργο C# στο ενσωματωμένο περιβάλλον ανάπτυξης (IDE) που προτιμάτε και προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 2: Εισαγάγετε τους απαραίτητους χώρους ονομάτων

Προσθέστε τα ακόλουθα χρησιμοποιώντας οδηγίες στην αρχή του αρχείου C# για να εισαγάγετε τους απαιτούμενους χώρους ονομάτων:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Βήμα 3: Ορίστε τη διαδρομή προς τον κατάλογο εγγράφων

 Ορίστε τη διαδρομή προς τον κατάλογο εγγράφων σας χρησιμοποιώντας το`dataDir` μεταβλητός:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

## Βήμα 4: Δημιουργήστε ένα TextFragmentAbsorber

 Δημιουργώ ένα`TextFragmentAbsorber` αντικείμενο για να βρείτε όλες τις παρουσίες της φράσης αναζήτησης εισόδου:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Αντικαθιστώ`"\\d{4}-\\d{4}"` με το επιθυμητό μοτίβο κανονικής έκφρασης.

## Βήμα 5: Ενεργοποιήστε την αναζήτηση τυπικών εκφράσεων

 Ενεργοποιήστε την αναζήτηση τυπικών εκφράσεων ορίζοντας το`TextSearchOptions` ιδιότητα του απορροφητή:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Βήμα 6: Ανοίξτε και συνδέστε το έγγραφο PDF

 Δημιουργώ ένα`PdfContentEditor` αντικείμενο και συνδέστε το στο αρχείο προέλευσης PDF:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Αντικαθιστώ`"SearchRegularExpressionPage.pdf"` με το πραγματικό όνομα του αρχείου PDF σας.

## Βήμα 7: Αποδεχτείτε τον απορροφητή για τη σελίδα

Αποδεχτείτε τον απορροφητή για την επιθυμητή σελίδα του εγγράφου:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Αντικαθιστώ`1` με τον επιθυμητό αριθμό σελίδας.

## Βήμα 8: Προσθέστε υπερσυνδέσμους στο κείμενο που βρέθηκε

Κάντε βρόχο στα ανακτημένα τμήματα κειμένου και προσθέστε υπερσυνδέσμους σε αυτά:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Δημιουργήστε ένα ορθογώνιο με βάση τη θέση του τμήματος κειμένου
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Προσθέστε έναν σύνδεσμο Ιστού στο ορθογώνιο
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Αντικαθιστώ`"http://www.aspose.com"` με την επιθυμητή διεύθυνση URL υπερσύνδεσης.

## Βήμα 9: Αποθηκεύστε και κλείστε το τροποποιημένο έγγραφο

Αποθηκεύστε το τροποποιημένο έγγραφο και κλείστε το πρόγραμμα επεξεργασίας:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Φροντίστε να αντικαταστήσετε`"SearchTextAndAddHyperlink_out.pdf"` με το επιθυμητό όνομα αρχείου εξόδου.

### Δείγμα πηγαίου κώδικα για Αναζήτηση κειμένου και προσθήκη υπερ-σύνδεσης χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Δημιουργήστε αντικείμενο απορροφητή για να βρείτε όλες τις εμφανίσεις της φράσης αναζήτησης εισόδου
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Ενεργοποίηση αναζήτησης κανονικών εκφράσεων
absorber.TextSearchOptions = new TextSearchOptions(true);
// Άνοιγμα εγγράφου
PdfContentEditor editor = new PdfContentEditor();
// Σύνδεση αρχείου PDF πηγής
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Αποδεχτείτε τον απορροφητήρα για τη σελίδα
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Περιηγηθείτε στα θραύσματα
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, μπλε, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## συμπέρασμα

Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να αναζητάτε συγκεκριμένο κείμενο σε ένα έγγραφο PDF, να προσθέτετε υπερσυνδέσμους στο κείμενο που βρέθηκε και να αποθηκεύετε το τροποποιημένο έγγραφο χρησιμοποιώντας το Aspose.PDF για .NET. Αυτό το σεμινάριο παρείχε έναν οδηγό βήμα προς βήμα, από τη ρύθμιση του έργου έως την εκτέλεση των απαιτούμενων ενεργειών. Τώρα μπορείτε να ενσωματώσετε αυτόν τον κώδικα στα δικά σας έργα C# για να χειριστείτε κείμενο και να προσθέσετε υπερσυνδέσμους σε αρχεία PDF.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός του σεμιναρίου "Αναζήτηση κειμένου και προσθήκη υπερσυνδέσμου";

Α: Το σεμινάριο "Αναζήτηση κειμένου και προσθήκη υπερσύνδεσης" στοχεύει να δείξει πώς να χρησιμοποιείτε τη βιβλιοθήκη Aspose.PDF για .NET για αναζήτηση συγκεκριμένου κειμένου σε ένα έγγραφο PDF, προσθήκη υπερσυνδέσμων στο κείμενο που βρέθηκε και, στη συνέχεια, αποθήκευση του τροποποιημένου εγγράφου. Το σεμινάριο παρέχει έναν ολοκληρωμένο οδηγό και δείγματα κώδικα C# για να επεξηγήσει τη διαδικασία βήμα προς βήμα.

#### Ε: Πώς βοηθά αυτό το σεμινάριο στην προσθήκη υπερσυνδέσμων σε συγκεκριμένο κείμενο σε ένα έγγραφο PDF;

Α: Αυτό το σεμινάριο σάς καθοδηγεί στη διαδικασία χρήσης της βιβλιοθήκης Aspose.PDF για να εντοπίσετε συγκεκριμένο κείμενο σε ένα έγγραφο PDF, να εφαρμόσετε μια υπερ-σύνδεση στο αναγνωρισμένο κείμενο και να αποθηκεύσετε το τροποποιημένο PDF. Καλύπτει βασικά βήματα όπως η ρύθμιση του έργου, η φόρτωση του εγγράφου, η ενεργοποίηση της αναζήτησης κανονικών εκφράσεων και η προσθήκη υπερσυνδέσμων στο κείμενο που βρέθηκε.

#### Ε: Ποιες προϋποθέσεις χρειάζονται για να ακολουθήσετε αυτό το σεμινάριο;

Α: Πριν ξεκινήσετε, θα πρέπει να έχετε μια βασική κατανόηση της γλώσσας προγραμματισμού C#. Επιπλέον, πρέπει να έχετε εγκατεστημένη τη βιβλιοθήκη Aspose.PDF για .NET, την οποία μπορείτε να λάβετε από τον ιστότοπο του Aspose ή να εγκαταστήσετε χρησιμοποιώντας το NuGet στο έργο σας.

#### Ε: Πώς μπορώ να ρυθμίσω το έργο μου για να ακολουθήσω αυτό το σεμινάριο;

Α: Ξεκινήστε δημιουργώντας ένα νέο έργο C# στο προτιμώμενο περιβάλλον ολοκληρωμένης ανάπτυξης (IDE). Στη συνέχεια, προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET, η οποία θα σας επιτρέψει να χρησιμοποιήσετε τις δυνατότητες της βιβλιοθήκης στο έργο σας.

#### Ε: Μπορώ να προσθέσω υπερσυνδέσμους σε συγκεκριμένο κείμενο χρησιμοποιώντας αυτό το σεμινάριο;

Α: Ναι, αυτό το σεμινάριο εστιάζει συγκεκριμένα στην προσθήκη υπερσυνδέσμων σε συγκεκριμένο κείμενο σε ένα έγγραφο PDF. Δείχνει πώς να βρείτε και να εξαγάγετε το επιθυμητό κείμενο χρησιμοποιώντας κανονικές εκφράσεις, να δημιουργήσετε υπερσυνδέσμους που σχετίζονται με τα τμήματα κειμένου και να αποθηκεύσετε το τροποποιημένο PDF.

#### Ε: Πώς μπορώ να ορίσω το κείμενο που θέλω να αναζητήσω και να προσθέσω έναν υπερσύνδεσμο;

 Α: Για να καθορίσετε το κείμενο που θέλετε να αναζητήσετε και να προσθέσετε έναν υπερσύνδεσμο, δημιουργήστε ένα`TextFragmentAbsorber` αντικείμενο και ορίστε το μοτίβο του χρησιμοποιώντας το`Text` παράμετρος. Αντικαταστήστε το προεπιλεγμένο μοτίβο`"\\d{4}-\\d{4}"` στον κώδικα του σεμιναρίου με το επιθυμητό μοτίβο κανονικής έκφρασης.

#### Ε: Πώς μπορώ να ενεργοποιήσω την αναζήτηση κανονικών εκφράσεων για κείμενο;

 Α: Η αναζήτηση κανονικών εκφράσεων ενεργοποιείται δημιουργώντας ένα`TextSearchOptions` αντικείμενο και ορίζοντας την τιμή του σε`true` . Αντιστοιχίστε αυτό το αντικείμενο στο`TextSearchOptions` ιδιοκτησία του`TextFragmentAbsorber` παράδειγμα. Αυτό διασφαλίζει ότι το μοτίβο κανονικής έκφρασης εφαρμόζεται κατά την αναζήτηση κειμένου.

#### Ε: Πώς μπορώ να προσθέσω υπερσυνδέσμους στο κείμενο που βρήκα;

 Α: Αφού προσδιορίσετε τα θραύσματα κειμένου χρησιμοποιώντας το`TextFragmentAbsorber` , το σεμινάριο παρέχει έναν βρόχο για επανάληψη μέσα από αυτά τα τμήματα. Για κάθε τμήμα κειμένου, το σεμινάριο δείχνει πώς να ορίσετε το χρώμα του κειμένου σε μπλε και να δημιουργήσετε μια υπερ-σύνδεση χρησιμοποιώντας το`CreateWebLink` μέθοδος.

#### Ε: Ποια είναι τα βήματα για να αποθηκεύσετε το τροποποιημένο PDF με υπερσυνδέσμους;

 Α: Αφού προσθέσετε υπερσυνδέσμους στα επιθυμητά τμήματα κειμένου, χρησιμοποιήστε το`PdfContentEditor` κλάση για να αποθηκεύσετε το τροποποιημένο έγγραφο. Το δείγμα κώδικα του σεμιναρίου δείχνει πώς να αποθηκεύσετε το επεξεργασμένο PDF, να κλείσετε το πρόγραμμα επεξεργασίας και να εμφανίσετε ένα μήνυμα επιτυχίας.