---
title: Ορισμός λεζάντας κουμπιού ραδιοφώνου
linktitle: Ορισμός λεζάντας κουμπιού ραδιοφώνου
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να χρησιμοποιείτε το Aspose.PDF για .NET για να ορίσετε τη λεζάντα για ένα κουμπί επιλογής σε μορφή PDF.
type: docs
weight: 280
url: /el/net/programming-with-forms/set-radio-button-caption/
---
Σε αυτόν τον οδηγό, θα εξηγήσουμε βήμα προς βήμα πώς να χρησιμοποιήσετε τη βιβλιοθήκη Aspose.PDF για .NET για να ορίσετε τη λεζάντα ενός κουμπιού επιλογής σε μορφή PDF. Θα σας δείξουμε πώς να αποκτήσετε πρόσβαση στο πεδίο του κουμπιού επιλογής, να δημιουργήσετε μια νέα επιλογή κουμπιού επιλογής και να προσαρμόσετε τη λεζάντα του κουμπιού.

## Βήμα 1: Διαμόρφωση του καταλόγου εγγράφων

 Το πρώτο βήμα είναι να διαμορφώσετε τον κατάλογο εγγράφων όπου βρίσκεται η φόρμα PDF στην οποία θέλετε να εργαστείτε. Μπορείτε να χρησιμοποιήσετε το`dataDir` μεταβλητή για να καθορίσετε τη διαδρομή καταλόγου.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Φροντίστε να αντικαταστήσετε`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας.

## Βήμα 2: Φόρτωση της φόρμας πηγής PDF

 Σε αυτό το βήμα, θα φορτώσουμε τη φόρμα πηγής PDF χρησιμοποιώντας το`Aspose.Pdf.Facades.Form` κλάση του Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Βεβαιωθείτε ότι το αρχείο PDF που περιέχει τη φόρμα υπάρχει στον καθορισμένο κατάλογο εγγράφων.

## Βήμα 3: Επεξεργασία της λεζάντας του κουμπιού επιλογής

Θα κάνουμε κύκλο στα ονόματα των πεδίων της φόρμας και θα αναζητήσουμε πεδία κουμπιών επιλογής. Εάν βρεθεί ένα αντίστοιχο πεδίο, θα δημιουργήσουμε μια νέα επιλογή κουμπιού επιλογής με προσαρμοσμένη λεζάντα και θα την προσθέσουμε στο υπάρχον πεδίο.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Δημιουργήστε ένα αντικείμενο TextParagraph
TextParagraph par = new TextParagraph();
// Ορισμός θέσης παραγράφου
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Καθορίστε τη λειτουργία αναδίπλωσης λέξης
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Προσθέστε το νέο TextFragment στην παράγραφο
par.AppendLine(updatedFragment);
// Προσθέστε το TextParagraph χρησιμοποιώντας το TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Προσαρμόστε το κουμπί επιλογής υπότιτλων και άλλες ρυθμίσεις όπως απαιτείται.

## Βήμα 4: Αποθήκευση του PDF που προκύπτει

 Τώρα που τελειώσαμε με την τροποποίηση της λεζάντας του κουμπιού επιλογής, μπορούμε να αποθηκεύσουμε το PDF που προκύπτει χρησιμοποιώντας το`Save` μέθοδος του`Document` τάξη.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Βεβαιωθείτε ότι έχετε καθορίσει την πλήρη διαδρομή και το όνομα αρχείου για το PDF που προκύπτει.

### Δείγμα πηγαίου κώδικα για Ορισμός λεζάντας κουμπιού ραδιοφώνου χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Φόρτωση φόρμας πηγής PDF
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// Δημιουργία αντικειμένου TextParagraph
		TextParagraph par = new TextParagraph();
		// Ορισμός θέσης παραγράφου
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Καθορίστε τη λειτουργία αναδίπλωσης λέξης
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Προσθήκη νέου TextFragment στην παράγραφο
		par.AppendLine(updatedFragment);
		// Προσθέστε το TextParagraph χρησιμοποιώντας το TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Σύναψη

Σε αυτόν τον οδηγό, μάθαμε πώς να χρησιμοποιούμε τη βιβλιοθήκη Aspose.PDF για .NET για να ορίσουμε τη λεζάντα για ένα κουμπί επιλογής σε μορφή PDF. Ακολουθώντας τα βήματα που περιγράφονται, μπορείτε να προσαρμόσετε τις επιλογές του κουμπιού επιλογής και να αλλάξετε τη λεζάντα όπως απαιτείται. Μη διστάσετε να εξερευνήσετε περαιτέρω τις δυνατότητες του Aspose.PDF για .NET για να επεκτείνετε τις δυνατότητες χειρισμού αρχείων PDF.

### Συχνές ερωτήσεις

#### Ε: Μπορώ να χρησιμοποιήσω το Aspose.PDF για .NET για να ορίσω λεζάντες για κουμπιά επιλογής σε μορφή PDF;

Α: Ναι, μπορείτε να χρησιμοποιήσετε το Aspose.PDF για .NET για να ορίσετε λεζάντες για κουμπιά επιλογής σε μορφή PDF. Το παρεχόμενο δείγμα πηγαίου κώδικα δείχνει πώς μπορείτε να αποκτήσετε πρόσβαση στο πεδίο κουμπιού επιλογής, να δημιουργήσετε μια νέα επιλογή κουμπιού επιλογής με προσαρμοσμένη λεζάντα και να ενημερώσετε το υπάρχον πεδίο.

#### Ε: Πώς μπορώ να προσαρμόσω την εμφάνιση της λεζάντας του κουμπιού επιλογής, όπως το μέγεθος και το χρώμα της γραμματοσειράς;

 Α: Μπορείτε να προσαρμόσετε την εμφάνιση της λεζάντας του κουμπιού επιλογής προσαρμόζοντας τις ιδιότητες του`TextFragment` χρησιμοποιείται για τη λεζάντα. Για παράδειγμα, μπορείτε να ορίσετε τη γραμματοσειρά, το μέγεθος της γραμματοσειράς, το χρώμα, το διάστιχο και άλλες επιλογές μορφοποίησης κειμένου.

#### Ε: Είναι δυνατή η προσθήκη πολλαπλών επιλογών κουμπιών επιλογής με διαφορετικούς υπότιτλους σε μία ομάδα κουμπιών επιλογής;

Α: Ναι, μπορείτε να προσθέσετε πολλές επιλογές κουμπιών επιλογής με διαφορετικούς υπότιτλους σε μία ομάδα κουμπιών επιλογής. Κάθε επιλογή θα αντιπροσωπεύει μια διαφορετική επιλογή και οι χρήστες μπορούν να επιλέξουν μόνο μία επιλογή από την ομάδα.

#### Ε: Μπορώ να χρησιμοποιήσω το Aspose.PDF για .NET για να τροποποιήσω άλλα πεδία φόρμας σε ένα έγγραφο PDF;

Α: Ναι, το Aspose.PDF για .NET παρέχει ένα ολοκληρωμένο σύνολο δυνατοτήτων για τον χειρισμό διαφόρων πεδίων φόρμας σε ένα έγγραφο PDF, όπως πεδία κειμένου, πλαίσια ελέγχου, αναπτυσσόμενες λίστες και άλλα. Μπορείτε να χρησιμοποιήσετε τη βιβλιοθήκη για να ορίσετε τιμές, να τροποποιήσετε εμφανίσεις και να προσθέσετε διαδραστικότητα σε πεδία σχηματισμού.

#### Ε: Υποστηρίζει το Aspose.PDF για .NET την εργασία με αρχεία PDF που δημιουργούνται από άλλες πηγές, όπως σαρωμένα έγγραφα;

Α: Ναι, το Aspose.PDF για .NET υποστηρίζει την εργασία με αρχεία PDF που δημιουργούνται από διάφορες πηγές, συμπεριλαμβανομένων των σαρωμένων εγγράφων. Η βιβλιοθήκη παρέχει δυνατότητες OCR (Optical Character Recognition) για εξαγωγή κειμένου από σαρωμένα PDF και χειρισμό του περιεχομένου μέσω προγραμματισμού.