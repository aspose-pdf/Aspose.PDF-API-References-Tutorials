---
title: Выделить символ в PDF-файле
linktitle: Выделить символ в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как выделить символы в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 240
url: /ru/net/programming-with-text/highlight-character-in-pdf/
---
В этом уроке мы объясним, как выделить символы в PDF-файле с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс выделения символов в PDF-файле, используя предоставленный исходный код C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Сначала вам нужно указать путь к каталогу, в котором находится входной PDF-файл. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к вашему PDF-файлу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите PDF-документ

 Затем мы загружаем входной PDF-документ, используя`Aspose.Pdf.Document` сорт.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Шаг 3. Конвертируйте PDF в изображение

 Чтобы выделить символы, мы конвертируем PDF-документ в изображение с помощью`PdfConverter` сорт. Мы устанавливаем разрешение для преобразования и получаем изображение в виде`Bitmap` объект.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Шаг 4: Выделите персонажей

 Мы просматриваем каждую страницу PDF-документа и используем`TextFragmentAbsorber` объект, чтобы найти все слова на странице. Затем мы перебираем текстовые фрагменты, сегменты и символы, чтобы выделить их с помощью прямоугольников.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //Установите масштаб и трансформируйте
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Перелистывание страниц
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // Найдите все слова на странице
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Перебирать фрагменты текста
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Выделение персонажей
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Перебирать сегменты
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Выделить сегмент
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Перебирать символы
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Выделить персонажа
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

## Шаг 5. Сохраните выходное изображение

Наконец, мы сохраняем измененное изображение с выделенными символами в указанный выходной файл.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Пример исходного кода для выделения символов в PDF с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
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
				// Создайте объект TextAbsorber, чтобы найти все слова.
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Получить извлеченные фрагменты текста
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Перебирать фрагменты
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
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// www.aspose.com/purchase/default.aspx.");
}
```

## Заключение

В этом уроке вы узнали, как выделять символы в PDF-документе с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы можете выделить символы в PDF-файле и сохранить результат в виде изображения.

### Часто задаваемые вопросы

#### Вопрос: Какова цель урока «Выделение символов в PDF-файле»?

О: В учебнике «Выделение символов в PDF-файле» объясняется, как использовать библиотеку Aspose.PDF для .NET для выделения символов в PDF-документе. Учебное пособие содержит пошаговое руководство и исходный код C# для достижения этой цели.

#### Вопрос: Зачем мне выделять символы в PDF-документе?

О: Выделение символов в PDF-документе может быть полезно для различных целей, например для выделения определенного содержимого или повышения заметности и различимости определенного текста.

#### Вопрос: Как настроить каталог документов?

О: Чтобы настроить каталог документов:

1.  Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к каталогу, в котором находится входной PDF-файл.

#### Вопрос: Как загрузить PDF-документ и преобразовать его в изображение?

 О: В учебнике`Aspose.Pdf.Document` Класс используется для загрузки входного PDF-документа. Затем`PdfConverter` Класс используется для преобразования PDF-документа в изображение. Разрешение изображения установлено, и изображение извлекается в виде`Bitmap` объект.

#### Вопрос: Как выделить символы в изображении PDF-документа?

О: В этом руководстве вы проведете циклически по каждой странице PDF-документа, находя слова с помощью`TextFragmentAbsorber`и перебирать фрагменты текста, сегменты и символы, чтобы выделить их с помощью прямоугольников.

#### Вопрос: Могу ли я настроить внешний вид выделенных символов и сегментов?

О: Да, вы можете настроить внешний вид выделенных символов и сегментов, изменяя цвета и стили, используемые в операциях рисования.

#### Вопрос: Как сохранить измененное изображение с выделенными символами?

 О: В учебнике показано, как сохранить измененное изображение с выделенными символами в указанный выходной файл с помощью команды`Save` метод`Bitmap` сорт.

#### Вопрос: Требуется ли для работы с этим руководством действующая лицензия Aspose?

О: Да, для корректной работы этого руководства требуется действующая лицензия Aspose. Вы можете приобрести полную лицензию или получить 30-дневную временную лицензию на веб-сайте Aspose.