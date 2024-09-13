---
title: स्टाइल टेबल सेल
linktitle: स्टाइल टेबल सेल
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ टेबल सेल को स्टाइल करना सीखें। टेबल बनाने और कस्टमाइज़ करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 160
url: /hi/net/programming-with-tagged-pdf/style-table-cell/
---
.NET के लिए Aspose.PDF का उपयोग करके टेबल सेल को फ़ॉर्मेट करने के इस विस्तृत ट्यूटोरियल में आपका स्वागत है। इस गाइड में, हम आपको टेबल सेल को स्टाइल करने के तरीके को समझने में मदद करने के लिए दिए गए C# सोर्स कोड के प्रत्येक चरण को विस्तार से समझाएंगे। सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF इंस्टॉल किया है और शुरू करने से पहले अपना डेवलपमेंट एनवायरनमेंट सेट अप किया है।

## चरण 1: वातावरण की स्थापना

आरंभ करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF का उपयोग करने के लिए अपने विकास परिवेश को कॉन्फ़िगर किया है। इसमें Aspose.PDF लाइब्रेरी को इंस्टॉल करना और इसे संदर्भित करने के लिए अपने प्रोजेक्ट को कॉन्फ़िगर करना शामिल है।

## चरण 2: दस्तावेज़ बनाना

इस चरण में, हम एक नया दस्तावेज़ ऑब्जेक्ट Aspose.PDF बनाएंगे।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ निर्माण
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

हमने एक नया दस्तावेज़ बनाया है और दस्तावेज़ का शीर्षक और भाषा निर्धारित की है।

## चरण 3: मूल संरचना तत्व प्राप्त करना

इस चरण में हम अपने दस्तावेज़ के लिए मूल संरचना तत्व प्राप्त करेंगे।

```csharp
// मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;
```

हमें मूल संरचना तत्व मिल गया है जो सरणी तत्वों के लिए एक कंटेनर के रूप में काम करेगा।

## चरण 4: सरणी संरचना तत्व बनाना

अब आइए अपने दस्तावेज़ के लिए एक नया तालिका संरचना तत्व बनाएं।

```csharp
// सरणी संरचना तत्व बनाएँ
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

हमने एक नया ऐरे स्ट्रक्चर एलिमेंट बनाया है और इसे रूट स्ट्रक्चर एलिमेंट में जोड़ा है। हमने टेबल हेडर, बॉडी और फ़ुटर एलिमेंट भी बनाए हैं।

## चरण 5: तालिका शीर्षलेख जोड़ना

इस चरण में हम अपनी तालिका में तालिका शीर्षलेख जोड़ेंगे।

```csharp
// तालिका में पंक्तियों और स्तंभों की संख्या
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// तालिका शीर्ष पंक्ति बनाएँ
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

हमने अपनी तालिका के लिए एक शीर्ष पंक्ति बनाई और पृष्ठभूमि रंग, बॉर्डर, मार्जिन और संरेखण जैसे स्वरूपण गुणों के साथ शीर्ष कोशिकाएं जोड़ीं।

## चरण 6: तालिका बॉडी पंक्तियाँ जोड़ना

अब आइए अपनी तालिका में तालिका बॉडी पंक्तियाँ जोड़ें।
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

हमने प्रत्येक टेबल सेल पर पुनरावृत्ति करने के लिए लूप का उपयोग करके टेबल के मुख्य भाग में पंक्तियाँ जोड़ीं। हमने प्रत्येक सेल के लिए फ़ॉर्मेटिंग गुण सेट किए, जैसे कि पृष्ठभूमि का रंग, बॉर्डर, मार्जिन, टेक्स्ट संरेखण, आदि।

## चरण 7: फ़ुटर जोड़ना

अंत में, हम अपनी तालिका में तालिका फ़ुटर जोड़ेंगे।

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

हमने अपनी तालिका के लिए एक पाद लेख बनाया और उसमें पाठ के साथ पाद लेख कक्ष जोड़े।



## चरण 8: टैग किए गए PDF दस्तावेज़ को सहेजना

अब जबकि हमने स्टाइल्ड तालिका के साथ अपना दस्तावेज़ बना लिया है, हम इसे टैग किए गए PDF दस्तावेज़ के रूप में सहेजेंगे।

```csharp
// टैग किए गए PDF दस्तावेज़ को सहेजें
document.Save(dataDir + "StyleTableCell.pdf");
```

हमने टैग किए गए पीडीएफ दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेज लिया।

## चरण 9: PDF/UA अनुपालन सत्यापन

इसके बाद, हम अपने दस्तावेज़ की PDF/UA अनुरूपता की पुष्टि करेंगे।

```csharp
// पीडीएफ/यूए अनुपालन जांच
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

हमने टैग किए गए पीडीएफ दस्तावेज़ को अपलोड किया और एक XML रिपोर्ट तैयार करके इसकी पीडीएफ/यूए अनुपालना की पुष्टि की।

### .NET के लिए Aspose.PDF का उपयोग करके स्टाइल टेबल सेल के लिए नमूना स्रोत कोड 
```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ बनाएँ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;

// तालिका संरचना तत्व बनाएँ
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// टैग किए गए पीडीएफ दस्तावेज़ सहेजें
document.Save(dataDir + "StyleTableCell.pdf");

// PDF/UA अनुपालन की जाँच करना
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके टेबल सेल को कैसे स्टाइल किया जाए। हमने देखा कि दस्तावेज़ कैसे बनाया जाता है, हेडर, बॉडी रो और फ़ुटर के साथ टेबल कैसे जोड़ा जाता है और सेल स्टाइल को कैसे कस्टमाइज़ किया जाता है। अंत में, हमने टैग किए गए PDF दस्तावेज़ को सहेजा और इसके PDF/UA अनुपालन को मान्य किया। अब आप अपने .NET अनुप्रयोगों में टेबल बनाने और स्टाइल करने के लिए .NET के लिए Aspose.PDF का उपयोग कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके तालिका कक्षों को प्रारूपित करने पर इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: इस ट्यूटोरियल का उद्देश्य .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ में टेबल सेल को स्टाइल करने के तरीके पर एक व्यापक गाइड प्रदान करना है। इसमें टेबल सेल फ़ॉर्मेटिंग को समझने और लागू करने में आपकी मदद करने के लिए चरण-दर-चरण निर्देश और C# स्रोत कोड उदाहरण शामिल हैं।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए पूर्वापेक्षाएँ क्या हैं?

उत्तर: आरंभ करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF स्थापित कर लिया है और अपना विकास वातावरण सेट कर लिया है। इसमें Aspose.PDF लाइब्रेरी को संदर्भित करने के लिए अपने प्रोजेक्ट को कॉन्फ़िगर करना शामिल है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके एक नया PDF दस्तावेज़ कैसे बनाऊं?

 उत्तर: एक नया पीडीएफ दस्तावेज़ बनाने के लिए, आपको एक इंस्टेंटिएट करना होगा`Document` Aspose.PDF लाइब्रेरी से ऑब्जेक्ट। प्रदान किया गया C# स्रोत कोड दर्शाता है कि दस्तावेज़ कैसे बनाया जाता है और उसका शीर्षक और भाषा कैसे सेट की जाती है।

#### प्रश्न: पीडीएफ दस्तावेज़ में मूल संरचना तत्व का क्या महत्व है?

उत्तर: मूल संरचना तत्व अन्य संरचना तत्वों के लिए एक कंटेनर के रूप में कार्य करता है, जो पीडीएफ दस्तावेज़ की सामग्री को व्यवस्थित और वर्गीकृत करने में मदद करता है। यह दस्तावेज़ की तार्किक संरचना स्थापित करने में महत्वपूर्ण भूमिका निभाता है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके तालिका संरचना तत्व कैसे बना सकता हूं और इसकी उपस्थिति को अनुकूलित कर सकता हूं?

 उत्तर: आप इसका उपयोग करके एक तालिका संरचना तत्व बना सकते हैं`CreateTableElement()` विधि। प्रदान किया गया स्रोत कोड यह दर्शाता है कि पृष्ठभूमि रंग, बॉर्डर, मार्जिन और संरेखण जैसे गुणों को सेट करके तालिका के स्वरूप को कैसे अनुकूलित किया जाए, जिसमें उसका शीर्षलेख, मुख्य भाग और पादलेख शामिल है।

#### प्रश्न: क्या मैं तालिका मुख्य भाग में अनेक पंक्तियाँ और कॉलम जोड़ सकता हूँ और उनके स्वरूपण को अनुकूलित कर सकता हूँ?

उत्तर: हां, ट्यूटोरियल यह दर्शाता है कि लूप का उपयोग करके टेबल बॉडी में कई पंक्तियाँ और कॉलम कैसे जोड़े जाते हैं। यह सेल फ़ॉर्मेटिंग को कस्टमाइज़ करने के उदाहरण भी प्रदान करता है, जैसे कि बैकग्राउंड कलर, बॉर्डर, टेक्स्ट अलाइनमेंट, फ़ॉन्ट स्टाइल, और बहुत कुछ।

#### प्रश्न: PDF/UA अनुपालन को मान्य करने का उद्देश्य क्या है, और मैं यह मान्यकरण कैसे कर सकता हूँ?

 उत्तर: PDF/UA अनुपालन को मान्य करने से यह सुनिश्चित होता है कि PDF दस्तावेज़ पहुँच मानकों का पालन करता है, जिससे यह विकलांग उपयोगकर्ताओं के लिए अधिक सुलभ हो जाता है। ट्यूटोरियल दिखाता है कि PDF/UA अनुरूपता को कैसे सत्यापित किया जाए`Validate()` विधि का उपयोग करें और एक XML रिपोर्ट तैयार करें।

#### प्रश्न: मैं इन अवधारणाओं को अपने .NET अनुप्रयोगों पर कैसे लागू कर सकता हूं?

उत्तर: आप अपने स्वयं के .NET अनुप्रयोगों में टेबल सेल फ़ॉर्मेटिंग को लागू करने के लिए गाइड के रूप में दिए गए C# स्रोत कोड उदाहरणों का उपयोग कर सकते हैं। अपनी आवश्यकताओं के अनुरूप कोड को अनुकूलित करें और इसे अपनी परियोजनाओं में एकीकृत करें।

#### प्रश्न: क्या PDF दस्तावेज़ों में तालिका कक्षों की स्टाइलिंग के लिए कोई अनुशंसित सर्वोत्तम अभ्यास हैं?

उत्तर: टेबल सेल को स्टाइल करते समय, अपने दर्शकों की ज़रूरतों पर विचार करें, जिसमें पहुँच संबंधी ज़रूरतें भी शामिल हैं। पठनीयता बढ़ाने के लिए विपरीत रंग, उचित फ़ॉन्ट और स्पष्ट सेल संरेखण का उपयोग करें। इसके अतिरिक्त, पहुँच मानकों को पूरा करने के लिए PDF/UA अनुपालन को मान्य करें।

#### प्रश्न: PDF दस्तावेज़ में बदलाव के लिए मैं .NET के लिए Aspose.PDF की अन्य कौन सी विशेषताएं देख सकता हूँ?

उत्तर: .NET के लिए Aspose.PDF PDF दस्तावेज़ हेरफेर के लिए कई सुविधाएँ प्रदान करता है, जिसमें टेक्स्ट निष्कर्षण, छवि प्रविष्टि, फ़ॉर्म फ़ील्ड प्रबंधन, डिजिटल हस्ताक्षर और बहुत कुछ शामिल है। अतिरिक्त कार्यक्षमताओं के बारे में जानने के लिए आधिकारिक दस्तावेज़ और संसाधन देखें।
