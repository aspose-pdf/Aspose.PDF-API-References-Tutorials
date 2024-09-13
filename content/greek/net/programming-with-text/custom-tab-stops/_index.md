---
title: Η προσαρμοσμένη καρτέλα σταματά σε αρχείο PDF
linktitle: Η προσαρμοσμένη καρτέλα σταματά σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να δημιουργείτε προσαρμοσμένες θέσεις καρτελών σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 120
url: /el/net/programming-with-text/custom-tab-stops/
---

Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία δημιουργίας προσαρμοσμένων θέσεων καρτελών σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα.

## Απαιτήσεις
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Visual Studio ή οποιοσδήποτε άλλος μεταγλωττιστής C# είναι εγκατεστημένος στον υπολογιστή σας.
- Aspose.PDF για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από τον επίσημο ιστότοπο του Aspose ή να χρησιμοποιήσετε έναν διαχειριστή πακέτων όπως το NuGet για να το εγκαταστήσετε.

## Βήμα 1: Ρύθμιση του έργου
1. Δημιουργήστε ένα νέο έργο C# στο περιβάλλον ανάπτυξης που προτιμάτε.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 2: Εισαγάγετε τους απαιτούμενους χώρους ονομάτων
Στο αρχείο κώδικα όπου θέλετε να δημιουργήσετε προσαρμοσμένες στάσεις καρτελών, προσθέστε τα ακόλουθα χρησιμοποιώντας οδηγίες στο επάνω μέρος του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Βήμα 3: Ορίστε τον κατάλογο εγγράφων
 Στον κώδικα, εντοπίστε τη γραμμή που λέει`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με τη διαδρομή προς τον κατάλογο όπου είναι αποθηκευμένα τα έγγραφά σας.

## Βήμα 4: Δημιουργήστε μια νέα παρουσία εγγράφου
 Δημιουργήστε ένα νέο`Document` αντικείμενο προσθέτοντας την ακόλουθη γραμμή κώδικα:

```csharp
Document _pdfdocument = new Document();
```

## Βήμα 5: Προσθέστε μια σελίδα στο έγγραφο
 Προσθέστε μια νέα σελίδα στο έγγραφο χρησιμοποιώντας το`Add` μέθοδος του`Pages` συλλογή. Στον παρεχόμενο κωδικό, η νέα σελίδα εκχωρείται στη μεταβλητή`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Βήμα 6: Δημιουργήστε προσαρμοσμένες στάσεις καρτελών
 Δημιουργία α`TabStops` αντικείμενο και προσθέστε προσαρμοσμένες στάσεις καρτελών σε αυτό. Ορίστε τον τύπο στοίχισης και τον τύπο του οδηγού για κάθε στοπ καρτέλας.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Βήμα 7: Δημιουργήστε θραύσματα κειμένου με στάσεις καρτελών
 Δημιουργώ`TextFragment` αντικείμενα και περάστε τους τις προσαρμοσμένες στάσεις καρτελών. Χρησιμοποιήστε τους ειδικούς χαρακτήρες`#$TAB` για να υποδείξετε τις καρτέλες στο κείμενο.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Βήμα 8: Αποθηκεύστε το έγγραφο PDF
 Αποθηκεύστε το έγγραφο PDF χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Δείγμα πηγαίου κώδικα για προσαρμοσμένες καρτέλες που χρησιμοποιούν το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Σύναψη
Έχετε δημιουργήσει επιτυχώς ένα έγγραφο PDF με προσαρμοσμένες καρτέλες χρησιμοποιώντας το Aspose.PDF για .NET. Το αρχείο PDF που προκύπτει μπορεί τώρα να βρεθεί στην καθορισμένη διαδρομή αρχείου εξόδου.

### Συχνές ερωτήσεις

#### Ε: Ποιο είναι το επίκεντρο αυτού του σεμιναρίου;

Α: Αυτό το σεμινάριο επικεντρώνεται στο να σας καθοδηγήσει στη διαδικασία δημιουργίας προσαρμοσμένων θέσεων καρτελών σε ένα αρχείο PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα για να επιτευχθεί αυτό.

#### Ε: Ποιους χώρους ονομάτων πρέπει να εισάγω για αυτόν τον οδηγό;

Α: Στο αρχείο κώδικα όπου θέλετε να δημιουργήσετε προσαρμοσμένες θέσεις καρτελών, εισαγάγετε τους ακόλουθους χώρους ονομάτων στην αρχή του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Ε: Πώς καθορίζω τον κατάλογο εγγράφων;

 Α: Στον κώδικα, βρείτε τη γραμμή`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

#### Ε: Πώς μπορώ να δημιουργήσω μια νέα παρουσία εγγράφου;

 Α: Στο Βήμα 4, θα δημιουργήσετε ένα νέο`Document` αντικείμενο χρησιμοποιώντας τον παρεχόμενο κωδικό.

#### Ε: Πώς μπορώ να προσθέσω μια σελίδα στο έγγραφο;

 Α: Στο Βήμα 5, θα προσθέσετε μια νέα σελίδα στο έγγραφο χρησιμοποιώντας το`Add` μέθοδος του`Pages` συλλογή.

#### Ε: Πώς μπορώ να δημιουργήσω προσαρμοσμένες στάσεις καρτελών;

 Α: Στο Βήμα 6, θα δημιουργήσετε ένα`TabStops` αντικείμενο και προσθέστε προσαρμοσμένες στάσεις καρτελών σε αυτό. Θα ορίσετε επίσης τύπους στοίχισης και οδηγού για κάθε στάση καρτέλας.

#### Ε: Πώς μπορώ να δημιουργήσω θραύσματα κειμένου με στοπ καρτελών;

 Α: Στο Βήμα 7, θα δημιουργήσετε`TextFragment` αντικείμενα και περάστε τους τις προσαρμοσμένες στάσεις καρτελών. Θα χρησιμοποιήσετε τους ειδικούς χαρακτήρες`#$TAB` για να υποδείξετε τις καρτέλες στο κείμενο.

#### Ε: Πώς μπορώ να αποθηκεύσω το έγγραφο PDF;

 Α: Στο Βήμα 8, θα αποθηκεύσετε το έγγραφο PDF χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

#### Ε: Ποιο είναι το κύριο στοιχείο από αυτό το σεμινάριο;

Α: Ακολουθώντας αυτό το σεμινάριο, έχετε μάθει πώς να δημιουργείτε ένα έγγραφο PDF με προσαρμοσμένες καρτέλες χρησιμοποιώντας το Aspose.PDF για .NET. Αυτό μπορεί να είναι χρήσιμο για την οργάνωση και τη στοίχιση κειμένου με δομημένο τρόπο.