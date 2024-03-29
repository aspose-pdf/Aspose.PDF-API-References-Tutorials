---
title: पीडीएफ दस्तावेज़ में निकालें जावास्क्रिप्ट जोड़ें
linktitle: दस्तावेज़ में निकालें जावास्क्रिप्ट जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में जावास्क्रिप्ट को जोड़ने और हटाने का तरीका जानें। दस्तावेज़-स्तरीय स्क्रिप्टिंग के लिए कोड ट्यूटोरियल के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 30
url: /hi/net/programming-with-document/addremovejavascripttodoc/
---
पीडीएफ दस्तावेज़ में जावास्क्रिप्ट जोड़ने और हटाने के लिए, हम .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करेंगे। यह शक्तिशाली लाइब्रेरी हमें .NET अनुप्रयोगों में पीडीएफ फाइलों में हेरफेर करने की अनुमति देती है। .NET के लिए Aspose.PDF का उपयोग करके जावास्क्रिप्ट जोड़ने और हटाने के लिए नीचे दिए गए चरण-दर-चरण निर्देशों का पालन करें।

## चरण 1: एक नया पीडीएफ दस्तावेज़ बनाएं

 का एक नया उदाहरण बनाकर शुरुआत करें`Document` .NET के लिए Aspose.PDF द्वारा प्रदान की गई कक्षा। यह पीडीएफ दस्तावेज़ के रूप में काम करेगा जहां हम जावास्क्रिप्ट जोड़ेंगे।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## चरण 2: दस्तावेज़ स्तर पर जावास्क्रिप्ट जोड़ें

 दस्तावेज़ स्तर पर जावास्क्रिप्ट जोड़ने के लिए, का उपयोग करें`JavaScript` की संपत्ति`Document` कक्षा। जावास्क्रिप्ट शब्दकोश में कुंजियों को जावास्क्रिप्ट फ़ंक्शन निर्दिष्ट करें।

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 इस ट्यूटोरियल में, हमने दो जावास्क्रिप्ट फ़ंक्शन जोड़े हैं,`func1` और`func2`, पीडीएफ दस्तावेज़ के लिए।

## चरण 3: दस्तावेज़ स्तर जावास्क्रिप्ट हटाएँ

 दस्तावेज़ स्तर पर जावास्क्रिप्ट को हटाने के लिए, पीडीएफ दस्तावेज़ को लोड करें और एक्सेस करें`JavaScript`शब्दकोष। कुंजियों पर पुनरावृति करें और वांछित जावास्क्रिप्ट फ़ंक्शन को हटा दें।

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 इस ट्यूटोरियल में, हम हटाते हैं`func1` पीडीएफ दस्तावेज़ से जावास्क्रिप्ट फ़ंक्शन।

## चरण 4: परिवर्तन सहेजें और सत्यापित करें

संशोधित पीडीएफ दस्तावेज़ सहेजें और परिवर्तनों को सत्यापित करें।

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

यह कोड संशोधित पीडीएफ दस्तावेज़ को सहेजेगा और सफलता संदेश प्रदर्शित करेगा।

### .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ों से जावास्क्रिप्ट जोड़ें, निकालें के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// दस्तावेज़ स्तर जावास्क्रिप्ट हटाएँ
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## निष्कर्ष

इस लेख में, हमने .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ों से जावास्क्रिप्ट को जोड़ने और हटाने के लिए चरण-दर-चरण मार्गदर्शिका प्रदान की है। निर्देशों का पालन करके और दिए गए कोड ट्यूटोरियल का उपयोग करके, आप आसानी से जावास्क्रिप्ट को अपने पीडीएफ दस्तावेजों में शामिल कर सकते हैं और जरूरत पड़ने पर इसे हटा सकते हैं। जावास्क्रिप्ट आपकी पीडीएफ फाइलों में गतिशील कार्यक्षमता और अन्तरक्रियाशीलता को सक्षम बनाता है, जिससे उपयोगकर्ता अनुभव बढ़ता है।


### पीडीएफ दस्तावेज़ में जावास्क्रिप्ट जोड़ने और हटाने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF क्या है?

उ: .NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में पीडीएफ फाइलों में प्रभावी ढंग से हेरफेर करने की अनुमति देती है। यह पीडीएफ दस्तावेज़ों के साथ प्रोग्रामेटिक रूप से काम करने के लिए व्यापक सुविधाएँ प्रदान करता है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में JavaScript कैसे जोड़ सकता हूँ?

 उ: आप इसका उपयोग करके दस्तावेज़ स्तर पर जावास्क्रिप्ट जोड़ सकते हैं`JavaScript` की संपत्ति`Document` कक्षा। बस जावास्क्रिप्ट शब्दकोश में कुंजियों को जावास्क्रिप्ट फ़ंक्शन असाइन करें।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से JavaScript हटा सकता हूँ?

 उ: हां, आप पीडीएफ दस्तावेज़ तक पहुंच कर जावास्क्रिप्ट को हटा सकते हैं`JavaScript` शब्दकोश और वांछित जावास्क्रिप्ट फ़ंक्शन को हटाना।

#### प्रश्न: क्या .NET के लिए Aspose.PDF पेशेवर परियोजनाओं के लिए उपयुक्त है?

उत्तर: बिल्कुल, .NET के लिए Aspose.PDF का व्यापक रूप से PDF हेरफेर और पीढ़ी कार्यों के लिए पेशेवर परियोजनाओं में उपयोग किया जाता है। यह उच्च प्रदर्शन और विश्वसनीय कार्यक्षमता प्रदान करता है।

#### प्रश्न: पीडीएफ दस्तावेज़ में जावास्क्रिप्ट जोड़ने से क्या लाभ मिलते हैं?

उ: पीडीएफ दस्तावेज़ में जावास्क्रिप्ट जोड़ने से आप इंटरैक्टिव और गतिशील पीडीएफ फाइलें बनाने में सक्षम हो जाते हैं। आप फ़ॉर्म सत्यापन लागू कर सकते हैं, गणना कर सकते हैं, और उपयोगकर्ता अनुभव को बढ़ाने के लिए विभिन्न इंटरैक्टिविटी सुविधाएँ जोड़ सकते हैं।