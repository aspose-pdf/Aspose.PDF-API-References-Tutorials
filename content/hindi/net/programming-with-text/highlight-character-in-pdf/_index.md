---
title: पीडीएफ फाइल में कैरेक्टर को हाइलाइट करें
linktitle: पीडीएफ फाइल में कैरेक्टर को हाइलाइट करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में वर्णों को हाइलाइट करना सीखें।
type: docs
weight: 240
url: /hi/net/programming-with-text/highlight-character-in-pdf/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ फाइल में अक्षरों को कैसे हाइलाइट किया जाए। हम दिए गए C# स्रोत कोड का उपयोग करके पीडीएफ में वर्णों को हाइलाइट करने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यकताएं

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET लाइब्रेरी के लिए Aspose.PDF स्थापित किया गया।
- C# प्रोग्रामिंग की बुनियादी समझ।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस निर्देशिका के लिए पथ सेट करना होगा जहां आपकी इनपुट पीडीएफ फाइल स्थित है। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` आपकी पीडीएफ फाइल के पथ के साथ परिवर्तनीय।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: पीडीएफ दस्तावेज़ लोड करें

 इसके बाद, हम इसका उपयोग करके इनपुट पीडीएफ दस्तावेज़ लोड करते हैं`Aspose.Pdf.Document` कक्षा।

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## चरण 3: पीडीएफ को छवि में बदलें

 वर्णों को हाइलाइट करने के लिए, हम पीडीएफ दस्तावेज़ को इसका उपयोग करके एक छवि में परिवर्तित करते हैं`PdfConverter` कक्षा। हम रूपांतरण के लिए रिज़ॉल्यूशन सेट करते हैं और छवि को पुनः प्राप्त करते हैं`Bitmap` वस्तु।

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## चरण 4: वर्णों को हाइलाइट करें

 हम पीडीएफ दस्तावेज़ के प्रत्येक पृष्ठ को लूप करते हैं और इसका उपयोग करते हैं`TextFragmentAbsorber` पृष्ठ के सभी शब्दों को खोजने के लिए ऑब्जेक्ट करें। फिर हम आयतों का उपयोग करके उन्हें हाइलाइट करने के लिए पाठ के अंशों, खंडों और वर्णों पर पुनरावृति करते हैं।

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //पैमाना निर्धारित करें और परिवर्तन करें
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // पृष्ठों के माध्यम से लूप करें
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // पृष्ठ में सभी शब्द ढूंढें
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // पाठ अंशों के माध्यम से लूप करें
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // पात्रों को हाइलाइट करें
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // खंडों के माध्यम से लूप करें
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // खंड को हाइलाइट करें
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // पात्रों के माध्यम से लूप करें
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // चरित्र को हाइलाइट करें
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## चरण 5: आउटपुट छवि सहेजें

अंत में, हम संशोधित छवि को हाइलाइट किए गए वर्णों के साथ निर्दिष्ट आउटपुट फ़ाइल में सहेजते हैं।

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ में हाइलाइट कैरेक्टर के लिए नमूना स्रोत कोड 
```csharp
try
{
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// सभी शब्दों को खोजने के लिए TextAbsorber ऑब्जेक्ट बनाएं
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// निकाले गए पाठ अंश प्राप्त करें
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// टुकड़ों के माध्यम से लूप करें
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx");
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ दस्तावेज़ में अक्षरों को कैसे हाइलाइट किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को निष्पादित करके, आप पीडीएफ में वर्णों को हाइलाइट कर सकते हैं और आउटपुट को एक छवि के रूप में सहेज सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में कैरेक्टर हाइलाइट करें" ट्यूटोरियल का उद्देश्य क्या है?

उ: "पीडीएफ फाइल में कैरेक्टर हाइलाइट करें" ट्यूटोरियल बताता है कि पीडीएफ दस्तावेज़ के भीतर वर्णों को हाइलाइट करने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। ट्यूटोरियल इसे प्राप्त करने के लिए चरण-दर-चरण मार्गदर्शिका और C# स्रोत कोड प्रदान करता है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में पात्रों को हाइलाइट क्यों करना चाहूंगा?

उ: पीडीएफ दस्तावेज़ में वर्णों को हाइलाइट करना विभिन्न उद्देश्यों के लिए उपयोगी हो सकता है, जैसे विशिष्ट सामग्री पर जोर देना या कुछ पाठ को अधिक दृश्यमान और अलग बनाना।

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे सेट करूँ?

उ: दस्तावेज़ निर्देशिका स्थापित करने के लिए:

1.  प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` उस निर्देशिका के पथ के साथ परिवर्तनीय जहां आपकी इनपुट पीडीएफ फ़ाइल स्थित है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ को कैसे लोड करूं और इसे एक छवि में कैसे परिवर्तित करूं?

 ए: ट्यूटोरियल में,`Aspose.Pdf.Document` इनपुट पीडीएफ दस्तावेज़ को लोड करने के लिए क्लास का उपयोग किया जाता है। फिर`PdfConverter` पीडीएफ दस्तावेज़ को एक छवि में बदलने के लिए क्लास का उपयोग किया जाता है। छवि का रिज़ॉल्यूशन सेट किया गया है, और छवि को पुनः प्राप्त किया गया है`Bitmap` वस्तु।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ छवि में पात्रों को कैसे उजागर करूं?

उ: ट्यूटोरियल आपको पीडीएफ दस्तावेज़ के प्रत्येक पृष्ठ के माध्यम से लूपिंग की प्रक्रिया के माध्यम से मार्गदर्शन करता है, जिसका उपयोग करके शब्द ढूंढते हैं`TextFragmentAbsorber`, और आयतों का उपयोग करके उन्हें हाइलाइट करने के लिए पाठ के टुकड़ों, खंडों और वर्णों के माध्यम से पुनरावृत्ति करना।

#### प्रश्न: क्या मैं हाइलाइट किए गए पात्रों और खंडों की उपस्थिति को अनुकूलित कर सकता हूं?

उ: हां, आप ड्राइंग संचालन में उपयोग किए गए रंगों और शैलियों को संशोधित करके हाइलाइट किए गए पात्रों और खंडों की उपस्थिति को अनुकूलित कर सकते हैं।

#### प्रश्न: मैं संशोधित छवि को हाइलाइट किए गए वर्णों के साथ कैसे सहेजूं?

 उ: ट्यूटोरियल दर्शाता है कि संशोधित छवि को हाइलाइट किए गए वर्णों के साथ निर्दिष्ट आउटपुट फ़ाइल में कैसे सहेजा जाए`Save` की विधि`Bitmap` कक्षा।

#### प्रश्न: क्या इस ट्यूटोरियल के लिए वैध Aspose लाइसेंस आवश्यक है?

उत्तर: हां, इस ट्यूटोरियल को सही ढंग से काम करने के लिए एक वैध Aspose लाइसेंस की आवश्यकता है। आप Aspose वेबसाइट से पूर्ण लाइसेंस खरीद सकते हैं या 30-दिवसीय अस्थायी लाइसेंस प्राप्त कर सकते हैं।