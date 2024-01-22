---
title: Αποκτήστε πόρο σχολιασμού
linktitle: Αποκτήστε πόρο σχολιασμού
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς μπορείτε να ανακτήσετε τον πόρο ενός σχολιασμού χρησιμοποιώντας το Aspose.PDF για .NET με αυτόν τον οδηγό βήμα προς βήμα.
type: docs
weight: 90
url: /el/net/annotations/getresourceofannotation/
---
Το παράδειγμα δείχνει πώς να αποκτήσετε πόρο σχολιασμού με το Aspose.PDF για .NET. Για να λάβετε τον πόρο ενός σχολιασμού χρησιμοποιώντας το Aspose.PDF για .NET, ακολουθήστε τα εξής βήματα:

## Βήμα 1: Ορίστε τη διαδρομή του καταλόγου όπου βρίσκεται το έγγραφο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Ανοίξτε το έγγραφο PDF που περιέχει τον σχολιασμό του οποίου τον πόρο θέλετε να λάβετε.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Βήμα 3: Δημιουργήστε έναν σχολιασμό.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Βήμα 4: Προσθέστε τον σχολιασμό σε μια σελίδα του εγγράφου.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Βήμα 5: Αποθηκεύστε το έγγραφο.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Βήμα 6: Ανοίξτε το τροποποιημένο έγγραφο.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Βήμα 7: Λάβετε τη δράση του σχολιασμού.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Βήμα 7: Λάβετε την απόδοση της δράσης.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Βήμα 8: Λάβετε το κλιπ πολυμέσων.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Βήμα 9: Λάβετε την προδιαγραφή αρχείου.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Βήμα 10: Διαβάστε τα δεδομένα των μέσων.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## Βήμα 11: Εκτυπώστε το όνομα της απόδοσης και τη λειτουργία απόδοσης.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να λάβετε τον πόρο ενός σχολιασμού σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET.

### Παράδειγμα πηγαίου κώδικα για Λήψη πόρων σχολιασμού χρησιμοποιώντας το Aspose.PDF για .NET:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Άνοιγμα εγγράφου
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Δημιουργία σχολιασμού
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Αποθήκευση εγγράφου
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Άνοιγμα εγγράφου
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Λάβετε δράση του σχολιασμού
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Λάβετε απόδοση της δράσης απόδοσης
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Κλιπ πολυμέσων
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Τα δεδομένα των μέσων είναι προσβάσιμα στο FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε πώς να αποκτήσετε τον πόρο ενός συγκεκριμένου σχολιασμού από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα και χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα C#, οι προγραμματιστές μπορούν εύκολα να έχουν πρόσβαση και να διαχειρίζονται τους σχολιασμούς, συμπεριλαμβανομένων των σχολιασμών απόδοσης, στα έγγραφά τους PDF.

### Συχνές ερωτήσεις

#### Ε: Τι είναι η απόδοση στο πλαίσιο των σχολιασμών PDF;

Α: Στο πλαίσιο των σχολιασμών PDF, μια απόδοση είναι μια παρουσίαση περιεχομένου πολυμέσων. Επιτρέπει την ενσωμάτωση πολυμέσων, όπως ήχου ή βίντεο, μέσα στο έγγραφο PDF. Ο σχολιασμός απόδοσης καθορίζει τα μέσα που θα παρουσιαστούν και τον τρόπο αναπαραγωγής τους.

#### Ε: Μπορώ να λάβω το όνομα του αρχείου πολυμέσων που σχετίζεται με έναν σχολιασμό απόδοσης;

Α: Ναι, μπορείτε να λάβετε το όνομα του αρχείου πολυμέσων που σχετίζεται με έναν σχολιασμό απόδοσης χρησιμοποιώντας το Aspose.PDF για .NET. Το όνομα του αρχείου πολυμέσων είναι προσβάσιμο μέσω του`FileSpecification` απο`MediaClip` αντικείμενο.

#### Ε: Μπορεί το Aspose.PDF για .NET να εξαγάγει αρχεία πολυμέσων από έναν σχολιασμό απόδοσης;

Α: Ναι, το Aspose.PDF για .NET μπορεί να εξάγει τα δεδομένα πολυμέσων από έναν σχολιασμό απόδοσης, ο οποίος περιλαμβάνει περιεχόμενο ήχου ή βίντεο, και να το αποθηκεύσει ως ξεχωριστό αρχείο.

#### Ε: Πώς μπορώ να έχω πρόσβαση στα δεδομένα πολυμέσων ενός σχολιασμού απόδοσης;

 Α: Τα δεδομένα πολυμέσων ενός σχολιασμού απόδοσης είναι προσβάσιμα μέσω του`FileSpecification.Contents` ιδιοκτησία του`MediaClipData` αντικείμενο.

#### Ε: Μπορώ να τροποποιήσω τα μέσα που σχετίζονται με έναν σχολιασμό απόδοσης χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Το Aspose.PDF για .NET παρέχει μεθόδους πρόσβασης και τροποποίησης των δεδομένων πολυμέσων που σχετίζονται με έναν σχολιασμό απόδοσης. Μπορείτε να ενημερώσετε ή να αντικαταστήσετε το αρχείο πολυμέσων που χρησιμοποιείται από έναν σχολιασμό απόδοσης.