---
title: Προσθήκη περιγράμματος κειμένου σε αρχείο PDF
linktitle: Προσθήκη περιγράμματος κειμένου σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς μπορείτε να προσθέσετε ένα περίγραμμα κειμένου σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 70
url: /el/net/programming-with-text/add-text-border/
---
Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία προσθήκης περιγράμματος κειμένου σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα.

## Απαιτήσεις
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Visual Studio ή οποιοσδήποτε άλλος μεταγλωττιστής C# είναι εγκατεστημένος στον υπολογιστή σας.
- Aspose.PDF για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από τον επίσημο ιστότοπο του Aspose ή να χρησιμοποιήσετε έναν διαχειριστή πακέτων όπως το NuGet για να το εγκαταστήσετε.

## Βήμα 1: Ρύθμιση του έργου
1. Δημιουργήστε ένα νέο έργο C# στο περιβάλλον ανάπτυξης που προτιμάτε.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 2: Εισαγάγετε τους απαιτούμενους χώρους ονομάτων
Στο αρχείο κώδικα όπου θέλετε να προσθέσετε το περίγραμμα κειμένου, προσθέστε τα ακόλουθα χρησιμοποιώντας την οδηγία στο επάνω μέρος του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Βήμα 3: Ορίστε τον κατάλογο εγγράφων
 Στον κώδικα, εντοπίστε τη γραμμή που λέει`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με τη διαδρομή προς τον κατάλογο όπου είναι αποθηκευμένα τα έγγραφά σας.

## Βήμα 4: Δημιουργήστε ένα νέο αντικείμενο Document
 Δημιουργήστε ένα νέο`Document` αντικείμενο προσθέτοντας την ακόλουθη γραμμή κώδικα:

```csharp
Document pdfDocument = new Document();
```

## Βήμα 5: Προσθέστε μια σελίδα στο έγγραφο
 Προσθέστε μια νέα σελίδα στο έγγραφο χρησιμοποιώντας το`Add` μέθοδος του`Pages`συλλογή. Στον παρεχόμενο κωδικό, η νέα σελίδα εκχωρείται στη μεταβλητή`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Βήμα 6: Δημιουργήστε ένα TextFragment
 Δημιουργώ ένα`TextFragment` αντικείμενο και παρέχετε το επιθυμητό κείμενο. Ορίστε τη θέση του τμήματος κειμένου χρησιμοποιώντας το`Position` ιδιοκτησία. Στον παρεχόμενο κωδικό, το κείμενο ορίζεται σε "κύριο κείμενο" και τοποθετείται στο (100, 600) στη σελίδα.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Βήμα 7: Ορισμός ιδιοτήτων κειμένου
Προσαρμόστε τις ιδιότητες του κειμένου όπως μέγεθος γραμματοσειράς, τύπος γραμματοσειράς, χρώμα φόντου, χρώμα προσκηνίου κ.λπ. Στον παρεχόμενο κώδικα, ιδιότητες όπως μέγεθος γραμματοσειράς, γραμματοσειρά, χρώμα φόντου, χρώμα προσκηνίου και χρώμα χάραξης έχουν οριστεί για το τμήμα κειμένου.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Βήμα 8: Ενεργοποιήστε το περίγραμμα κειμένου
 Για να ενεργοποιήσετε το περίγραμμα κειμένου, ορίστε το`DrawTextRectangleBorder`ιδιότητα του τμήματος κειμένου`TextState` προς την`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Βήμα 9: Προσθέστε το TextFragment στη σελίδα
 Χρησιμοποιήστε το`TextBuilder` τάξη για να προσθέσετε το`TextFragment` αντικείμενο στη σελίδα.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Βήμα 10: Αποθηκεύστε το έγγραφο PDF
 Αποθηκεύστε το έγγραφο PDF χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο. Καθορίστε τη διαδρομή αρχείου εξόδου που ορίσατε στο Βήμα 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Δείγμα πηγαίου κώδικα για Προσθήκη περιγράμματος κειμένου χρησιμοποιώντας Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Δημιουργία νέου αντικειμένου εγγράφου
Document pdfDocument = new Document();
// Λάβετε συγκεκριμένη σελίδα
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Δημιουργία τμήματος κειμένου
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Ορισμός ιδιοτήτων κειμένου
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Ορίστε την ιδιότητα StrokingColor για σχεδίαση περιγράμματος (χαϊδεύοντας) γύρω από το ορθογώνιο κειμένου
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Ορίστε την τιμή της ιδιότητας DrawTextRectangleBorder σε true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Αποθηκεύστε το έγγραφο
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## συμπέρασμα
Προσθέσατε με επιτυχία ένα περίγραμμα κειμένου στο έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Το αρχείο PDF που προκύπτει μπορεί τώρα να βρεθεί στην καθορισμένη διαδρομή αρχείου εξόδου.

### Συχνές ερωτήσεις

#### Ε: Ποια είναι η κύρια εστίαση αυτού του σεμιναρίου;

Α: Αυτό το σεμινάριο σάς καθοδηγεί στη διαδικασία προσθήκης περιγράμματος κειμένου σε αρχείο PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα για να επιτευχθεί αυτό.

#### Ε: Ποιους χώρους ονομάτων πρέπει να εισαγάγω για αυτόν τον οδηγό;

Α: Στο αρχείο κώδικα όπου θέλετε να προσθέσετε το περίγραμμα κειμένου, εισαγάγετε τους ακόλουθους χώρους ονομάτων στην αρχή του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Ε: Πώς καθορίζω τον κατάλογο εγγράφων;

 Α: Στον κωδικό, εντοπίστε τη γραμμή`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

#### Ε: Πώς μπορώ να δημιουργήσω ένα αντικείμενο Document;

 Α: Στο Βήμα 4, θα δημιουργήσετε ένα νέο`Document` αντικείμενο χρησιμοποιώντας την ακόλουθη γραμμή κώδικα:

```csharp
Document pdfDocument = new Document();
```

#### Ε: Πώς μπορώ να προσθέσω μια σελίδα στο έγγραφο;

 Α: Στο Βήμα 5, θα προσθέσετε μια νέα σελίδα στο έγγραφο χρησιμοποιώντας το`Add` μέθοδος του`Pages` συλλογή:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### Ε: Πώς μπορώ να δημιουργήσω ένα TextFragment και να ορίσω τη θέση του;

 Α: Στο Βήμα 6, θα δημιουργήσετε ένα`TextFragment`αντικείμενο και ορίστε τη θέση του στη σελίδα χρησιμοποιώντας το`Position` ιδιοκτησία:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### Ε: Πώς μπορώ να προσαρμόσω τις ιδιότητες κειμένου, συμπεριλαμβανομένου του περιγράμματος κειμένου;

Α: Στο Βήμα 7, θα προσαρμόσετε διάφορες ιδιότητες κειμένου, όπως μέγεθος γραμματοσειράς, τύπος γραμματοσειράς, χρώμα φόντου, χρώμα προσκηνίου και περίγραμμα κειμένου:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### Ε: Πώς μπορώ να προσθέσω το TextFragment στο έγγραφο PDF;

 Α: Στο Βήμα 9, θα χρησιμοποιήσετε το`TextBuilder` τάξη για να προσθέσετε το`TextFragment` αντικείμενο στη σελίδα:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Ε: Πώς μπορώ να αποθηκεύσω το έγγραφο PDF που προκύπτει;

 Α: Αφού προσθέσετε το κείμενο με περίγραμμα, χρησιμοποιήστε το`Save` μέθοδος του`Document` αντικείμενο αποθήκευσης του εγγράφου PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### Ε: Ποιο είναι το κύριο στοιχείο από αυτό το σεμινάριο;

Α: Ακολουθώντας αυτό το σεμινάριο, μάθατε με επιτυχία πώς να βελτιώσετε το έγγραφο PDF προσθέτοντας ένα περίγραμμα κειμένου χρησιμοποιώντας το Aspose.PDF για .NET. Αυτό μπορεί να είναι ιδιαίτερα χρήσιμο για να δώσετε έμφαση σε συγκεκριμένο περιεχόμενο κειμένου στα αρχεία PDF σας.