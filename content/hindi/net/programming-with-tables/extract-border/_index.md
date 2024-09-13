---
title: पीडीएफ फाइल में बॉर्डर निकालें
linktitle: पीडीएफ फाइल में बॉर्डर निकालें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में बॉर्डर निकालने का तरीका जानें।
type: docs
weight: 80
url: /hi/net/programming-with-tables/extract-border/
---
इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में बॉर्डर कैसे निकालें। हम C# में सोर्स कोड को चरण दर चरण समझाएँगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि PDF दस्तावेज़ से बॉर्डर कैसे निकालें और उसे इमेज के रूप में कैसे सेव करें। चलिए शुरू करते हैं!

## चरण 1: वातावरण की स्थापना
सबसे पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF के साथ अपना C# डेवलपमेंट एनवायरनमेंट सेट अप कर लिया है। लाइब्रेरी में संदर्भ जोड़ें और आवश्यक नेमस्पेस आयात करें।

## चरण 2: पीडीएफ दस्तावेज़ लोड करना
इस चरण में, हम निर्दिष्ट फ़ाइल से पीडीएफ दस्तावेज़ लोड करते हैं।

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

"आपकी दस्तावेज़ निर्देशिका" को उस वास्तविक निर्देशिका से प्रतिस्थापित करना सुनिश्चित करें जहां आपकी पीडीएफ फाइल स्थित है।

## चरण 3: किनारा निकालना
हम दस्तावेज़ में निहित कार्यों को दोहराकर पीडीएफ दस्तावेज़ से बॉर्डर निकालेंगे।

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // सभी सामग्री संचालन की प्रक्रिया करें
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // ऑपरेशन के प्रकार की जाँच करें
         // ...
         // प्रत्येक ऑपरेशन को संसाधित करने के लिए कोड जोड़ें
     }
}
```

 हम एक बनाते हैं`graphicsState` ग्राफ़िक्स स्थिति को संग्रहीत करने के लिए स्टैक, निकाली गई सीमा को कैप्चर करने के लिए एक बिटमैप छवि,`GraphicsPath` ऑब्जेक्ट का उपयोग ड्राइंग पथों को संग्रहीत करने के लिए, तथा अन्य चरों का उपयोग स्थिति और रंगों को ट्रैक करने के लिए किया जाता है।

## चरण 4: लेनदेन प्रसंस्करण
इस चरण में, हम बॉर्डर निकालने के लिए दस्तावेज़ के प्रत्येक ऑपरेशन को संसाधित करते हैं।

```csharp
// ऑपरेशन के प्रकार की जाँच करें
if (opSaveState != null)
{
     // पिछली स्थिति को सहेजें और वर्तमान स्थिति को स्टैक के शीर्ष पर धकेलें
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // वर्तमान स्थिति को हटाएं और पिछली स्थिति को पुनर्स्थापित करें
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // वर्तमान परिवर्तन मैट्रिक्स पुनः प्राप्त करें
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // वर्तमान मैट्रिक्स को राज्य मैट्रिक्स से गुणा करें
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // अंतिम आरेखण बिंदु को अद्यतन करें
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // रेखा खींचने की प्रक्रिया
     // ...
     // रेखा खींचने के लिए कोड जोड़ें
}
// ...
// अन्य कार्यों के लिए else if ब्लॉक जोड़ें
```

हम शर्तों का उपयोग करके ऑपरेशन के प्रकार की जांच करते हैं और प्रत्येक ऑपरेशन के लिए उपयुक्त कोड चलाते हैं।

## चरण 5: बैकअप छवि
अंत में, हम निकाले गए बॉर्डर वाले बिटमैप चित्र को एक निर्दिष्ट फ़ाइल में सहेज लेते हैं।

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

आउटपुट छवि को सहेजने के लिए सही निर्देशिका और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.PDF का उपयोग करके बॉर्डर निकालने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// डिफ़ॉल्ट सीटीएम मैट्रिक्स मान 1,0,0,1,0,0 है
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//सिस्टम.ड्राइंग निर्देशांक प्रणाली शीर्ष बाएँ आधारित है, जबकि पीडीएफ निर्देशांक प्रणाली निचले बाएँ आधारित है, इसलिए हमें व्युत्क्रम मैट्रिक्स लागू करना होगा
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// सभी सामग्री आदेशों को संसाधित करें
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			// पिछली स्थिति को सहेजें और वर्तमान स्थिति को स्टैक के शीर्ष पर धकेलें
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// वर्तमान स्थिति को हटा दें और पिछली स्थिति को बहाल करें
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opCtm != null)
		{
			System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
				(float)opCtm.Matrix.A,
				(float)opCtm.Matrix.B,
				(float)opCtm.Matrix.C,
				(float)opCtm.Matrix.D,
				(float)opCtm.Matrix.E,
				(float)opCtm.Matrix.F);

			// वर्तमान मैट्रिक्स को राज्य मैट्रिक्स से गुणा करें
			((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से बॉर्डर कैसे निकाला जाता है। आप अन्य PDF दस्तावेज़ों से बॉर्डर निकालने के लिए इस चरण-दर-चरण मार्गदर्शिका का उपयोग कर सकते हैं।

### पीडीएफ फाइल में बॉर्डर निकालने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ फाइल से बॉर्डर निकालने का उद्देश्य क्या है?

उत्तर: पीडीएफ फाइल से बॉर्डर निकालना कई उद्देश्यों के लिए उपयोगी हो सकता है। यह आपको दस्तावेज़ के संरचनात्मक तत्वों, जैसे कि तालिकाओं, आरेखों या ग्राफ़िकल तत्वों को अलग करने और उनका विश्लेषण करने की अनुमति देता है। आप निकाले गए बॉर्डर का उपयोग पीडीएफ दस्तावेज़ के भीतर सामग्री के लेआउट, आयाम और स्थिति की पहचान करने के लिए कर सकते हैं।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ के भीतर विशिष्ट पृष्ठों या क्षेत्रों से बॉर्डर निकाल सकता हूं?

 उत्तर: हां, आप पीडीएफ दस्तावेज़ के भीतर विशिष्ट पृष्ठों या क्षेत्रों से बॉर्डर निकालने के लिए दिए गए C# स्रोत कोड को संशोधित कर सकते हैं।`doc.Pages` संग्रह और कस्टम मानदंड निर्दिष्ट करके, आप विशेष पृष्ठों या रुचि के क्षेत्रों से सीमा निकालने का विकल्प चुन सकते हैं।

#### प्रश्न: मैं आउटपुट छवि प्रारूप और गुणवत्ता को कैसे अनुकूलित कर सकता हूं?

 उत्तर: दिए गए C# कोड में, निकाले गए बॉर्डर को PNG इमेज के रूप में सहेजा जाता है। यदि आप आउटपुट इमेज प्रारूप बदलना चाहते हैं, तो आप इसे संशोधित कर सकते हैं।`ImageFormat.Png` पैरामीटर में`bitmap.Save` अन्य समर्थित छवि प्रारूपों, जैसे कि JPEG, BMP, या GIF के लिए विधि। इसके अतिरिक्त, आप अपनी आवश्यकताओं के आधार पर छवि गुणवत्ता या संपीड़न सेटिंग्स को समायोजित कर सकते हैं।

#### प्रश्न: निकाले गए बॉर्डर पर मैं अन्य कौन से कार्य कर सकता हूँ?

उत्तर: एक बार जब आप बॉर्डर को इमेज के रूप में निकाल लेते हैं, तो आप इमेज प्रोसेसिंग लाइब्रेरी या एल्गोरिदम का उपयोग करके इसे आगे प्रोसेस कर सकते हैं। आप इमेज का विश्लेषण कर सकते हैं, इमेज फ़िल्टर लगा सकते हैं, पैटर्न का पता लगा सकते हैं, या ज़रूरत पड़ने पर इमेज से टेक्स्ट निकालने के लिए OCR (ऑप्टिकल कैरेक्टर रिकॉग्निशन) कर सकते हैं।

#### प्रश्न: जटिल PDF दस्तावेज़ों से बॉर्डर निकालते समय क्या कोई सीमाएं या विचार हैं?

उत्तर: निष्कर्षण प्रक्रिया पीडीएफ दस्तावेज़ की जटिलता के आधार पर भिन्न हो सकती है। कई परतों, पारदर्शिता या उन्नत ग्राफ़िक्स वाले जटिल पीडीएफ को सीमा को सटीक रूप से निकालने के लिए अतिरिक्त प्रसंस्करण या समायोजन की आवश्यकता हो सकती है। विश्वसनीय परिणाम सुनिश्चित करने के लिए विभिन्न पीडीएफ दस्तावेज़ों पर निष्कर्षण प्रक्रिया का पूरी तरह से परीक्षण करना आवश्यक है।