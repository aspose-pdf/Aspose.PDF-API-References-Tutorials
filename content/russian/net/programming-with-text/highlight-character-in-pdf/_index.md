---
title: Выделение символа в PDF-файле
linktitle: Выделение символа в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как выделить символы в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 240
url: /ru/net/programming-with-text/highlight-character-in-pdf/
---
В этом уроке мы объясним, как выделить символы в файле PDF с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс выделения символов в PDF с помощью предоставленного исходного кода C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовые знания программирования на C#.

## Шаг 1: Настройте каталог документов

 Сначала вам нужно указать путь к каталогу, где находится ваш входной PDF-файл. Заменить`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменную с путем к вашему PDF-файлу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите PDF-документ

 Далее мы загружаем входной PDF-документ с помощью`Aspose.Pdf.Document` сорт.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Шаг 3: Преобразование PDF в изображение

 Чтобы выделить символы, мы преобразуем PDF-документ в изображение с помощью`PdfConverter` класс. Мы устанавливаем разрешение для преобразования и получаем изображение как`Bitmap` объект.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Шаг 4: Выделение символов

 Мы просматриваем каждую страницу PDF-документа и используем`TextFragmentAbsorber` объект для поиска всех слов на странице. Затем мы перебираем фрагменты текста, сегменты и символы, чтобы выделить их с помощью прямоугольников.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Установить масштаб и трансформировать
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Перебирать страницы
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //Найти все слова на странице
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Цикл по фрагментам текста
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

                 // Цикл по сегментам
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Выделить сегмент
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Перебор символов
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Выделитьхарактер
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

## Шаг 5: Сохраните полученное изображение.

Наконец, мы сохраняем измененное изображение с выделенными символами в указанный выходной файл.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Пример исходного кода для выделения символов в PDF с помощью Aspose.PDF для .NET 
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
				// Создайте объект TextAbsorber для поиска всех слов
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Получить извлеченные фрагменты текста
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Просмотрите фрагменты
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

В этом уроке вы узнали, как выделить символы в документе PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполняя предоставленный код C#, вы можете выделить символы в PDF и сохранить вывод в виде изображения.

### Часто задаваемые вопросы

#### В: Какова цель урока «Выделение символов в PDF-файле»?

A: В руководстве "Выделение символов в PDF-файле" объясняется, как использовать библиотеку Aspose.PDF для .NET для выделения символов в PDF-документе. В руководстве представлено пошаговое руководство и исходный код C# для достижения этой цели.

#### В: Зачем мне может понадобиться выделять символы в PDF-документе?

A: Выделение символов в PDF-документе может быть полезно для различных целей, например, чтобы подчеркнуть определенный контент или сделать определенный текст более заметным и различимым.

#### В: Как настроить каталог документов?

A: Чтобы настроить каталог документов:

1.  Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к каталогу, где находится ваш входной PDF-файл.

#### В: Как загрузить PDF-документ и преобразовать его в изображение?

 A: В этом уроке`Aspose.Pdf.Document` класс используется для загрузки входного PDF-документа. Затем,`PdfConverter` класс используется для преобразования документа PDF в изображение. Устанавливается разрешение изображения, и изображение извлекается как`Bitmap` объект.

#### В: Как выделить символы на изображении PDF-документа?

A: Учебник проведет вас через процесс просмотра каждой страницы документа PDF, находя слова с помощью`TextFragmentAbsorber`и перебирая фрагменты текста, сегменты и символы, выделяя их с помощью прямоугольников.

#### В: Могу ли я настроить внешний вид выделенных символов и сегментов?

A: Да, вы можете настроить внешний вид выделенных символов и сегментов, изменив цвета и стили, используемые в операциях рисования.

#### В: Как сохранить измененное изображение с выделенными символами?

 A: В руководстве показано, как сохранить измененное изображение с выделенными символами в указанный выходной файл с помощью`Save` Метод`Bitmap` сорт.

#### В: Требуется ли для этого руководства действующая лицензия Aspose?

A: Да, для корректной работы этого руководства требуется действующая лицензия Aspose. Вы можете приобрести полную лицензию или получить 30-дневную временную лицензию на веб-сайте Aspose.