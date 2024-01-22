---
title: Εξαγωγή παραγράφων σε αρχείο PDF
linktitle: Εξαγωγή παραγράφων σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να εξάγετε παραγράφους σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 160
url: /el/net/programming-with-text/extract-paragraphs/
---
Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία εξαγωγής παραγράφων σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα.

## Απαιτήσεις
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Visual Studio ή οποιοσδήποτε άλλος μεταγλωττιστής C# είναι εγκατεστημένος στον υπολογιστή σας.
- Aspose.PDF για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από τον επίσημο ιστότοπο του Aspose ή να χρησιμοποιήσετε έναν διαχειριστή πακέτων όπως το NuGet για να το εγκαταστήσετε.

## Βήμα 1: Ρύθμιση του έργου
1. Δημιουργήστε ένα νέο έργο C# στο περιβάλλον ανάπτυξης που προτιμάτε.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 2: Εισαγάγετε τους απαιτούμενους χώρους ονομάτων
Στο αρχείο κώδικα όπου θέλετε να εξαγάγετε παραγράφους, προσθέστε τα ακόλουθα χρησιμοποιώντας οδηγίες στο επάνω μέρος του αρχείου:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Βήμα 3: Ορίστε τον κατάλογο εγγράφων
 Στον κώδικα, εντοπίστε τη γραμμή που λέει`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με τη διαδρομή προς τον κατάλογο όπου είναι αποθηκευμένα τα έγγραφά σας.

## Βήμα 4: Ανοίξτε το έγγραφο PDF
 Ανοίξτε ένα υπάρχον έγγραφο PDF χρησιμοποιώντας το`Document`κατασκευαστή και περνώντας τη διαδρομή προς το αρχείο εισόδου PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Βήμα 5: Εξαγωγή παραγράφων
 Στιγμιότυπο το`ParagraphAbsorber` τάξη και χρησιμοποιήστε την`Visit` μέθοδος εξαγωγής παραγράφων από το έγγραφο.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Βήμα 6: Επαναλάβετε τις παραγράφους
Κάντε βρόχο στις παραγράφους που έχουν εξαχθεί για πρόσβαση στα περιεχόμενα του κειμένου. Χρησιμοποιήστε ένθετους βρόχους για να διασχίσετε τμήματα και γραμμές σε κάθε παράγραφο.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Δείγμα πηγαίου κώδικα για εξαγωγή παραγράφων χρησιμοποιώντας Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Ανοίξτε ένα υπάρχον αρχείο PDF
Document doc = new Document(dataDir + "input.pdf");
// Instantiate ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## συμπέρασμα
Έχετε εξαγάγει με επιτυχία παραγράφους από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Οι παραγράφοι που έχουν εξαχθεί έχουν εμφανιστεί στο παράθυρο της κονσόλας.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός αυτού του σεμιναρίου;

Α: Αυτό το σεμινάριο έχει σκοπό να σας καθοδηγήσει στη διαδικασία εξαγωγής παραγράφων από ένα αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ο συνοδευτικός πηγαίος κώδικας C# παρέχει πρακτικά βήματα για την επίτευξη αυτής της εργασίας.

#### Ε: Ποιους χώρους ονομάτων πρέπει να εισάγω;

Α: Στο αρχείο κώδικα όπου σκοπεύετε να εξαγάγετε παραγράφους, συμπεριλάβετε τα ακόλουθα χρησιμοποιώντας οδηγίες στην αρχή του αρχείου:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### Ε: Πώς καθορίζω τον κατάλογο εγγράφων;

 Α: Εντοπίστε τη γραμμή`string dataDir = "YOUR DOCUMENT DIRECTORY";` στον κωδικό και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

#### Ε: Πώς μπορώ να ανοίξω ένα υπάρχον έγγραφο PDF;

 Α: Στο Βήμα 4, θα ανοίξετε ένα υπάρχον έγγραφο PDF χρησιμοποιώντας το`Document` κατασκευαστή και παρέχοντας τη διαδρομή προς το αρχείο εισόδου PDF.

#### Ε: Πώς μπορώ να εξαγάγω παραγράφους από το έγγραφο;

 Α: Το βήμα 5 περιλαμβάνει τη δημιουργία μιας παρουσίας του`ParagraphAbsorber` τάξη και χρησιμοποιώντας την`Visit` μέθοδος εξαγωγής παραγράφων από το έγγραφο PDF.

#### Ε: Πώς μπορώ να επαναλάβω τις εξαγόμενες παραγράφους;

Α: Το Βήμα 6 σας καθοδηγεί στην αναζήτηση των παραγράφων που έχουν εξαχθεί. Οι ένθετοι βρόχοι χρησιμοποιούνται για τη διέλευση τμημάτων και γραμμών εντός κάθε παραγράφου, για να αποκτήσουν τελικά πρόσβαση και να εμφανίσουν τα περιεχόμενα του κειμένου.

#### Ε: Ποιο είναι το βασικό στοιχείο από αυτό το σεμινάριο;

Α: Ακολουθώντας αυτό το σεμινάριο, μάθατε πώς να εξάγετε παραγράφους από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Οι παραγράφοι που έχουν εξαχθεί έχουν εμφανιστεί στο παράθυρο της κονσόλας, παρέχοντάς σας πολύτιμες πληροφορίες για τη δομή περιεχομένου του εγγράφου.