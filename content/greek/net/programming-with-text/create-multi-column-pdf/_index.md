---
title: Δημιουργία Pdf πολλαπλών στηλών
linktitle: Δημιουργία Pdf πολλαπλών στηλών
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να δημιουργείτε ένα PDF πολλαπλών στηλών χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 110
url: /el/net/programming-with-text/create-multi-column-pdf/
---
Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία δημιουργίας ενός PDF πολλαπλών στηλών χρησιμοποιώντας το Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα.

## Απαιτήσεις
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Visual Studio ή οποιοσδήποτε άλλος μεταγλωττιστής C# είναι εγκατεστημένος στον υπολογιστή σας.
- Aspose.PDF για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από τον επίσημο ιστότοπο του Aspose ή να χρησιμοποιήσετε έναν διαχειριστή πακέτων όπως το NuGet για να το εγκαταστήσετε.

## Βήμα 1: Ρύθμιση του έργου
1. Δημιουργήστε ένα νέο έργο C# στο περιβάλλον ανάπτυξης που προτιμάτε.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 2: Εισαγάγετε τους απαιτούμενους χώρους ονομάτων
Στο αρχείο κώδικα όπου θέλετε να δημιουργήσετε ένα PDF πολλών στηλών, προσθέστε τα ακόλουθα χρησιμοποιώντας οδηγίες στο επάνω μέρος του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Βήμα 3: Ορίστε τον κατάλογο εγγράφων
 Στον κώδικα, εντοπίστε τη γραμμή που λέει`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με τη διαδρομή προς τον κατάλογο όπου είναι αποθηκευμένα τα έγγραφά σας.

## Βήμα 4: Δημιουργήστε μια νέα παρουσία εγγράφου
 Δημιουργήστε ένα νέο`Document` αντικείμενο προσθέτοντας την ακόλουθη γραμμή κώδικα:

```csharp
Document doc = new Document();
```

## Βήμα 5: Ορίστε τα περιθώρια της σελίδας
 Καθορίστε τις πληροφορίες αριστερού και δεξιού περιθωρίου για το αρχείο PDF χρησιμοποιώντας το`PageInfo.Margin` ιδιοκτησία του`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Βήμα 6: Προσθέστε μια σελίδα στο έγγραφο
 Προσθέστε μια νέα σελίδα στο έγγραφο χρησιμοποιώντας το`Add` μέθοδος του`Pages`συλλογή. Στον παρεχόμενο κωδικό, η νέα σελίδα εκχωρείται στη μεταβλητή`page`.

```csharp
Page page = doc.Pages.Add();
```

## Βήμα 7: Δημιουργήστε ένα αντικείμενο Graph και προσθέστε μια γραμμή
 Δημιούργησε ένα νέο`Graph` αντικείμενο με συγκεκριμένες διαστάσεις και προσθέστε μια γραμμή σε αυτό. Στη συνέχεια, προσθέστε το`Graph` αντίρρηση στο`Paragraphs` συλλογή της σελίδας.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Βήμα 8: Προσθέστε κείμενο επικεφαλίδας με μορφοποίηση HTML
 Δημιουργήστε ένα`HtmlFragment` αντικείμενο και ορίστε το περιεχόμενό του στο επιθυμητό κείμενο HTML. Στη συνέχεια, προσθέστε το θραύσμα στο`Paragraphs` συλλογή της σελίδας.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Βήμα 9: Δημιουργήστε ένα FloatingBox με πολλές στήλες
 Δημιουργώ ένα`FloatingBox` αντικείμενο και ορίστε τον αριθμό των στηλών και την απόσταση στηλών. Στη συνέχεια, προσθέστε θραύσματα κειμένου και μια γραμμή στο`Paragraphs` συλλογή των`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Βήμα 10: Αποθηκεύστε το έγγραφο PDF
 Αποθηκεύστε το έγγραφο PDF χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
doc.Save(dataDir);
```

### Δείγμα πηγαίου κώδικα για Δημιουργία Pdf πολλαπλών στηλών με χρήση Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// Καθορίστε τις πληροφορίες του αριστερού περιθωρίου για το αρχείο PDF
doc.PageInfo.Margin.Left = 40;
//Καθορίστε τις πληροφορίες του δεξιού περιθωρίου για το αρχείο PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Προσθέστε τη γραμμή στη συλλογή παραφράσεων του αντικειμένου ενότητας
page.Paragraphs.Add(graph1);
// Καθορίστε τις συντεταγμένες για τη γραμμή
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Δημιουργήστε μεταβλητές συμβολοσειράς με κείμενο που περιέχει ετικέτες html
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Δημιουργήστε παραγράφους κειμένου που περιέχουν κείμενο HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Προσθέστε τέσσερις στήλες στην ενότητα
box.ColumnInfo.ColumnCount = 2;
// Ορίστε την απόσταση μεταξύ των στηλών
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Δημιουργήστε ένα αντικείμενο γραφημάτων για να σχεδιάσετε μια γραμμή
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Καθορίστε τις συντεταγμένες για τη γραμμή
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Προσθέστε τη γραμμή στη συλλογή παραγράφων του αντικειμένου ενότητας
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Αποθήκευση αρχείου PDF
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## συμπέρασμα
Δημιουργήσατε επιτυχώς ένα PDF πολλαπλών στηλών χρησιμοποιώντας το Aspose.PDF για .NET. Το αρχείο PDF που προκύπτει μπορεί τώρα να βρεθεί στην καθορισμένη διαδρομή αρχείου εξόδου.

### Συχνές ερωτήσεις

#### Ε: Ποιο είναι το επίκεντρο αυτού του σεμιναρίου;

Αυτό το σεμινάριο επικεντρώνεται στο να σας καθοδηγήσει στη διαδικασία δημιουργίας ενός PDF πολλών στηλών χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα για να επιτευχθεί αυτό.

#### Ε: Ποιους χώρους ονομάτων πρέπει να εισάγω για αυτόν τον οδηγό;

Α: Στο αρχείο κώδικα όπου θέλετε να δημιουργήσετε ένα PDF πολλών στηλών, εισαγάγετε τους ακόλουθους χώρους ονομάτων στην αρχή του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Ε: Πώς καθορίζω τον κατάλογο εγγράφων;

 Α: Στον κώδικα, βρείτε τη γραμμή`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

#### Ε: Πώς μπορώ να δημιουργήσω μια νέα παρουσία εγγράφου;

 Α: Στο Βήμα 4, θα δημιουργήσετε ένα νέο`Document` αντικείμενο χρησιμοποιώντας τον παρεχόμενο κωδικό.

#### Ε: Πώς ορίζω τα περιθώρια της σελίδας;

 Α: Στο Βήμα 5, θα χρησιμοποιήσετε το`PageInfo.Margin` ιδιοκτησία του`Document` για να καθορίσετε τις πληροφορίες του αριστερού και του δεξιού περιθωρίου για το αρχείο PDF.

#### Ε: Πώς μπορώ να προσθέσω μια σελίδα στο έγγραφο;

 Α: Στο Βήμα 6, θα προσθέσετε μια νέα σελίδα στο έγγραφο χρησιμοποιώντας το`Add` μέθοδος του`Pages` συλλογή.

#### Ε: Πώς μπορώ να δημιουργήσω ένα αντικείμενο Graph και να προσθέσω μια γραμμή;

 Α: Στο Βήμα 7, θα δημιουργήσετε ένα νέο`Graph` αντικείμενο, προσθέστε μια γραμμή σε αυτό και, στη συνέχεια, προσθέστε το`Graph` αντίρρηση στο`Paragraphs` συλλογή της σελίδας.

#### Ε: Πώς μπορώ να προσθέσω κείμενο επικεφαλίδας με μορφοποίηση HTML;

 Α: Στο Βήμα 8, θα δημιουργήσετε ένα`HtmlFragment` αντικείμενο και ορίστε το περιεχόμενό του στο επιθυμητό κείμενο HTML και, στη συνέχεια, προσθέστε το τμήμα στο`Paragraphs` συλλογή της σελίδας.

#### Ε: Πώς μπορώ να δημιουργήσω ένα FloatingBox με πολλές στήλες;

 Α: Στο Βήμα 9, θα δημιουργήσετε ένα`FloatingBox` αντικείμενο με πολλές στήλες και διάστιχο στηλών και, στη συνέχεια, προσθέστε θραύσματα κειμένου και μια γραμμή στο`Paragraphs` συλλογή των`FloatingBox`.

#### Ε: Πώς μπορώ να αποθηκεύσω το έγγραφο PDF;

 Α: Στο Βήμα 10, θα αποθηκεύσετε το έγγραφο PDF χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

#### Ε: Ποιο είναι το κύριο στοιχείο από αυτό το σεμινάριο;

Α: Ακολουθώντας αυτό το σεμινάριο, μάθατε πώς να δημιουργείτε ένα έγγραφο PDF πολλών στηλών χρησιμοποιώντας το Aspose.PDF για .NET. Αυτό μπορεί να είναι χρήσιμο για την εμφάνιση περιεχομένου σε μια δομημένη και οργανωμένη διάταξη.