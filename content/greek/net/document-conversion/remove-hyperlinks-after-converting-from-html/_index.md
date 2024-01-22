---
title: Αφαιρέστε υπερσυνδέσμους μετά τη μετατροπή από το Html
linktitle: Αφαιρέστε υπερσυνδέσμους μετά τη μετατροπή από το Html
second_title: Aspose.PDF για Αναφορά API .NET
description: Οδηγός βήμα προς βήμα για την κατάργηση υπερσυνδέσμων μετά τη μετατροπή HTML σε PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 250
url: /el/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία κατάργησης υπερσυνδέσμων από ένα αρχείο PDF που δημιουργήθηκε από ένα αρχείο HTML χρησιμοποιώντας το Aspose.PDF για .NET. Οι υπερσύνδεσμοι είναι σύνδεσμοι με δυνατότητα κλικ που ενδέχεται να ανακατευθύνουν σε άλλες σελίδες ή ιστότοπους. Ακολουθώντας τα παρακάτω βήματα, θα μπορείτε να αφαιρέσετε υπερσυνδέσμους από το αρχείο PDF που προκύπτει.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι πληροίτε τις ακόλουθες προϋποθέσεις:

- Βασικές γνώσεις της γλώσσας προγραμματισμού C#.
- Η βιβλιοθήκη Aspose.PDF για .NET είναι εγκατεστημένη στο σύστημά σας.
- Ένα περιβάλλον ανάπτυξης όπως το Visual Studio.

## Βήμα 1: Φόρτωση αρχείου HTML και κατάργηση υπερσυνδέσμων
Σε αυτό το βήμα, θα φορτώσουμε το αρχείο HTML και θα αφαιρέσουμε τους υπερσυνδέσμους από το έγγραφο PDF που προκύπτει. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Φορτώστε το αρχείο HTML χρησιμοποιώντας τις επιλογές φόρτωσης HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Περιηγηθείτε στους σχολιασμούς της πρώτης σελίδας του εγγράφου
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Ελέγξτε αν ο σχολιασμός είναι σύνδεσμος
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Ελέγξτε εάν η ενέργεια είναι τύπου GoToURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Χρησιμοποιήστε έναν απορροφητή θραυσμάτων κειμένου για να βρείτε τα αντίστοιχα τμήματα κειμένου
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Πραγματοποιήστε βρόχο μέσω των ταιριασμένων τμημάτων κειμένου και αφαιρέστε χαρακτηριστικά από υπερσυνδέσμους
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Αφαιρέστε τον σχολιασμό από τη σελίδα
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Φροντίστε να αντικαταστήσετε`"YOUR DOCUMENTS DIRECTORY"` με τον πραγματικό κατάλογο όπου βρίσκεται το αρχείο HTML.

## Βήμα 2: Αποθήκευση του αρχείου PDF που προκύπτει
Τέλος, θα αποθηκεύσουμε το αρχείο PDF που προκύπτει χωρίς τους υπερσυνδέσμους. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
// Αποθηκεύστε το αρχείο PDF που προκύπτει
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Ο παραπάνω κώδικας αποθηκεύει το αρχείο PDF που προκύπτει με το όνομα αρχείου`"RemoveHyperlinksFromText_out.pdf"`.

### Παράδειγμα πηγαίου κώδικα για Κατάργηση υπερσυνδέσμων μετά τη μετατροπή από Html χρησιμοποιώντας Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, καλύψαμε τη διαδικασία βήμα προς βήμα κατάργησης υπερσυνδέσμων από ένα αρχείο PDF που δημιουργήθηκε από ένα αρχείο HTML χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας τις οδηγίες που περιγράφονται παραπάνω, θα μπορείτε να αφαιρέσετε με επιτυχία υπερσυνδέσμους από το αρχείο PDF που προκύπτει.

### Συχνές ερωτήσεις

#### Ε: Τι είναι το Aspose.PDF για .NET;

Α: Το Aspose.PDF για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται με έγγραφα PDF σε εφαρμογές C#. Προσφέρει ένα ευρύ φάσμα λειτουργιών, συμπεριλαμβανομένης της δυνατότητας μετατροπής αρχείων HTML σε PDF και χειρισμού περιεχομένου PDF.

#### Ε: Γιατί θα ήθελα να αφαιρέσω υπερσυνδέσμους από ένα αρχείο PDF;

Α: Υπάρχουν διάφοροι λόγοι για την κατάργηση υπερσυνδέσμων από ένα αρχείο PDF. Για παράδειγμα, μπορεί να θέλετε να εξαλείψετε εξωτερικούς συνδέσμους για σκοπούς εκτύπωσης ή αρχειοθέτησης ή να διασφαλίσετε ότι το περιεχόμενο PDF δεν είναι πλοηγήσιμο μέσω υπερσυνδέσμων.

#### Ε: Πώς μπορώ να φορτώσω ένα αρχείο HTML και να αφαιρέσω υπερσυνδέσμους χρησιμοποιώντας το Aspose.PDF για .NET;

 Α: Για να φορτώσετε ένα αρχείο HTML και να αφαιρέσετε υπερσυνδέσμους, μπορείτε να χρησιμοποιήσετε το Aspose.PDF για .NET`HtmlLoadOptions` τάξη. Επαναλάβετε τους σχολιασμούς των σελίδων PDF για να βρείτε σχολιασμούς συνδέσμων και να τροποποιήσετε τα χαρακτηριστικά τους.

#### Ε: Μπορώ να προσαρμόσω το όνομα αρχείου εξόδου για το PDF που προκύπτει;

Α: Ναι, μπορείτε να προσαρμόσετε το όνομα αρχείου εξόδου για το αρχείο PDF που προκύπτει τροποποιώντας τον κώδικα που αποθηκεύει το έγγραφο PDF. Απλώς αλλάξτε το επιθυμητό όνομα αρχείου στο`doc.Save()` μέθοδος.

#### Ε: Είναι δυνατή η επιλεκτική κατάργηση υπερσυνδέσμων με βάση ορισμένα κριτήρια;

Α: Ναι, μπορείτε να αφαιρέσετε επιλεκτικά υπερσυνδέσμους με βάση συγκεκριμένα κριτήρια. Για παράδειγμα, μπορείτε να επιλέξετε να αφαιρέσετε μόνο εξωτερικούς συνδέσμους ή συνδέσμους που παραπέμπουν σε συγκεκριμένες διευθύνσεις URL.