---
title: पीडीएफ फाइल में बुकमार्क पेज नंबर प्राप्त करें
linktitle: पीडीएफ फाइल में बुकमार्क पेज नंबर प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ आसानी से पीडीएफ फाइल में बुकमार्क पेज नंबर प्राप्त करें।
type: docs
weight: 60
url: /hi/net/programming-with-bookmarks/get-bookmark-page-number/
---
पीडीएफ फाइल में बुकमार्क से जुड़े पेज नंबर पुनर्प्राप्त करना नेविगेशन के लिए उपयोगी हो सकता है। .NET के लिए Aspose.PDF के साथ, आप निम्नलिखित स्रोत कोड का पालन करके आसानी से बुकमार्क की पृष्ठ संख्या प्राप्त कर सकते हैं:

## चरण 1: आवश्यक पुस्तकालय आयात करें

शुरू करने से पहले, आपको अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी आयात करनी होगी। यहाँ आवश्यक आयात निर्देश है:

```csharp
using Aspose.Pdf.Facades;
```

## चरण 2: दस्तावेज़ फ़ोल्डर में पथ सेट करें

 इस चरण में, आपको उस पीडीएफ फ़ाइल वाले फ़ोल्डर का पथ निर्दिष्ट करना होगा जिससे आप बुकमार्क पृष्ठ संख्याएँ निकालना चाहते हैं। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"`आपके दस्तावेज़ फ़ोल्डर के वास्तविक पथ के साथ निम्नलिखित कोड में:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 3: बुकमार्क संपादक बनाएं

 अब हम एक बनाएंगे`PdfBookmarkEditor` दस्तावेज़ के बुकमार्क में हेरफेर करने पर आपत्ति। निम्नलिखित कोड का प्रयोग करें:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## चरण 4: पीडीएफ फाइल खोलें

 इस चरण में, हम इसका उपयोग करके पीडीएफ फाइल खोलते हैं`BindPdf` बुकमार्क संपादक की विधि. यहाँ संबंधित कोड है:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## चरण 5: बुकमार्क निकालें

 अब हम इसका उपयोग करके दस्तावेज़ से बुकमार्क निकालेंगे`ExtractBookmarks` बुकमार्क संपादक की विधि. यहाँ संबंधित कोड है:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## चरण 6: बुकमार्क ब्राउज़ करें और पेज नंबर प्राप्त करें

 अंत में, हम निकाले गए बुकमार्क के माध्यम से लूप करते हैं और a का उपयोग करके प्रत्येक बुकमार्क से जुड़े पेज नंबर प्राप्त करते हैं`foreach` कुंडली। यहाँ संबंधित कोड है:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### .NET के लिए Aspose.PDF का उपयोग करके बुकमार्क पेज नंबर प्राप्त करने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// पीडीएफबुकमार्कएडिटर बनाएं
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// पीडीएफ फाइल खोलें
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// बुकमार्क निकालें
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## निष्कर्ष

बधाई हो! अब आपके पास .NET के लिए Aspose.PDF के साथ बुकमार्क पेज नंबर प्राप्त करने के लिए चरण-दर-चरण मार्गदर्शिका है। आप अपने पीडीएफ दस्तावेज़ों में प्रत्येक बुकमार्क से जुड़ी नेविगेशन जानकारी पुनर्प्राप्त करने के लिए इस कोड का उपयोग कर सकते हैं।

उन्नत बुकमार्क हेरफेर सुविधाओं पर अधिक जानकारी के लिए आधिकारिक Aspose.PDF दस्तावेज़ को अवश्य देखें।

### पीडीएफ फाइल में बुकमार्क पेज नंबर प्राप्त करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ फाइल में बुकमार्क क्या हैं?

उ: पीडीएफ फाइल में बुकमार्क नेविगेशनल सहायता हैं जो उपयोगकर्ताओं को दस्तावेज़ के भीतर विशिष्ट अनुभागों या पृष्ठों पर तुरंत जाने की अनुमति देते हैं। वे प्रासंगिक सामग्री के शॉर्टकट प्रदान करके उपयोगकर्ता अनुभव को बढ़ाते हैं।

#### प्रश्न: मैं पीडीएफ फाइल से बुकमार्क पेज नंबर क्यों पुनर्प्राप्त करना चाहूंगा?

उ: बुकमार्क पेज नंबर पुनर्प्राप्त करने से उपयोगकर्ताओं को दस्तावेज़ के माध्यम से अधिक प्रभावी ढंग से नेविगेट करने में मदद मिलती है, जिससे यह स्पष्ट संकेत मिलता है कि प्रत्येक बुकमार्क कहां जाता है। यह अनेक अनुभागों वाले लंबे दस्तावेज़ों के लिए विशेष रूप से उपयोगी है।

#### प्रश्न: मैं अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी कैसे आयात करूं?

उ: अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी आयात करने के लिए, निम्नलिखित आयात निर्देश का उपयोग करें:

```csharp
using Aspose.Pdf.Facades;
```

यह निर्देश आपको .NET के लिए Aspose.PDF द्वारा प्रदान की गई कक्षाओं और विधियों का उपयोग करने की अनुमति देता है।

#### प्रश्न: मैं दस्तावेज़ फ़ोल्डर का पथ कैसे निर्दिष्ट करूं?

 उत्तर: दिए गए स्रोत कोड में, बदलें`"YOUR DOCUMENT DIRECTORY"`उस पीडीएफ फ़ाइल वाले फ़ोल्डर के वास्तविक पथ के साथ जिसमें से आप बुकमार्क पेज नंबर निकालना चाहते हैं। यह सुनिश्चित करता है कि कोड लक्ष्य पीडीएफ फाइल का पता लगा सकता है।

#### प्रश्न: मैं एक बुकमार्क संपादक कैसे बनाऊं?

उ: बुकमार्क संपादक बनाने के लिए, निम्नलिखित कोड का उपयोग करें:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### प्रश्न: मैं बुकमार्क हेरफेर के लिए पीडीएफ फाइल कैसे खोलूं?

उ: बुकमार्क जानकारी निकालने के लिए पीडीएफ फाइल खोलने के लिए, निम्नलिखित कोड का उपयोग करें:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 प्रतिस्थापित करें`"GetBookmarks.pdf"` वास्तविक फ़ाइल नाम के साथ.

#### प्रश्न: मैं पीडीएफ फाइल से बुकमार्क कैसे निकालूं?

 उ: पीडीएफ फ़ाइल से बुकमार्क निकालने के लिए, का उपयोग करें`ExtractBookmarks` बुकमार्क संपादक की विधि:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### प्रश्न: मैं बुकमार्क पृष्ठ संख्याएँ कैसे पुनः प्राप्त और प्रदर्शित करूँ?

 ए: का उपयोग करके निकाले गए बुकमार्क के माध्यम से लूप करें`foreach` लूप करें और एक्सेस करें`PageNumber` प्रत्येक बुकमार्क की संपत्ति उसके संबंधित पृष्ठ क्रमांक को पुनः प्राप्त करने और प्रदर्शित करने के लिए:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### प्रश्न: क्या मैं इस दृष्टिकोण का उपयोग करके बुकमार्क गुणों को संशोधित कर सकता हूँ?

 उ: जबकि यह ट्यूटोरियल बुकमार्क पेज नंबर पुनर्प्राप्त करने पर केंद्रित है, आप इसका उपयोग करके अन्य बुकमार्क गुणों को संशोधित कर सकते हैं`Bookmark`वस्तु और संबंधित गुण।

#### प्रश्न: बुकमार्क जानकारी निकालने के बाद मैं अद्यतन पीडीएफ फाइल को कैसे सहेजूं?

उ: बुकमार्क निष्कर्षण मूल पीडीएफ फ़ाइल को संशोधित नहीं करता है। यदि आप कोई परिवर्तन सहेजना चाहते हैं, तो आप .NET के लिए Aspose.PDF द्वारा प्रदान की गई अन्य विधियों का उपयोग करके ऐसा कर सकते हैं।