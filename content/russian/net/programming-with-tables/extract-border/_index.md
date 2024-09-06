---
title: Извлечь границу в файл PDF
linktitle: Извлечь границу в файл PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как извлечь границу из PDF-файла с помощью Aspose.PDF для .NET.
type: docs
weight: 80
url: /ru/net/programming-with-tables/extract-border/
---
В этом уроке мы научимся извлекать границу из PDF-файла с помощью Aspose.PDF для .NET. Мы шаг за шагом объясним исходный код на C#. В конце этого урока вы узнаете, как извлечь границу из PDF-документа и сохранить ее как изображение. Начнем!

## Шаг 1: Настройка среды
Сначала убедитесь, что вы настроили среду разработки C# с Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2: Загрузка PDF-документа
На этом этапе мы загружаем PDF-документ из указанного файла.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» фактическим каталогом, в котором находится ваш PDF-файл.

## Шаг 3: Извлечение края
Мы извлечем границу из PDF-документа, повторяя операции, содержащиеся в документе.

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
     // Обработать все операции с контентом
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Проверьте тип операции
         // ...
         // Добавьте код для обработки каждой операции
     }
}
```

 Мы создаем`graphicsState` стек для хранения графических состояний, растровое изображение для захвата извлеченной границы,`GraphicsPath` объект для хранения путей рисования и других переменных для отслеживания состояния и цветов.

## Шаг 4: Обработка транзакции
На этом этапе мы обрабатываем каждую операцию документа для извлечения границы.

```csharp
// Проверьте тип операции
if (opSaveState != null)
{
     // Сохраните предыдущее состояние и поместите текущее состояние наверх стека.
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Удалить текущее состояние и восстановить предыдущее состояние
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Получить текущую матрицу преобразования
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Умножить текущую матрицу на матрицу состояния
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Обновить последнюю точку рисования
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Обработать рисунок линии
     // ...
     // Добавьте код для обработки рисования линии
}
// ...
// Добавьте блоки else if для других операций
```

Мы проверяем тип операции с помощью условий и запускаем соответствующий код для каждой операции.

## Шаг 5: Резервное копирование образа
Наконец, мы сохраняем растровое изображение, содержащее извлеченную границу, в указанный файл.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Обязательно укажите правильный каталог и имя файла для сохранения выходного изображения.

### Пример исходного кода для извлечения границы с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Значение матрицы ctm по умолчанию: 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Система координат System.Drawing расположена в верхнем левом углу, а система координат PDF — в нижнем левом углу, поэтому нам нужно применить матрицу инверсии.
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Обработать все команды содержимого
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
			//Сохранить предыдущее состояние и поместить текущее состояние наверх стека
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Удалить текущее состояние и восстановить предыдущее
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

			// Умножить текущую матрицу на матрицу состояния
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

## Заключение
В этом уроке мы узнали, как извлечь границу из документа PDF с помощью Aspose.PDF для .NET. Вы можете использовать это пошаговое руководство для извлечения границы из других документов PDF.

### Часто задаваемые вопросы по извлечению границы в файле PDF

#### В: Какова цель извлечения границы из PDF-файла?

A: Извлечение границы из файла PDF может быть полезным для различных целей. Это позволяет вам изолировать и анализировать структурные элементы документа, такие как таблицы, диаграммы или графические элементы. Вы можете использовать извлеченную границу для определения макета, размеров и позиционирования содержимого в документе PDF.

#### В: Могу ли я извлечь границу из определенных страниц или областей в документе PDF?

A: Да, вы можете изменить предоставленный исходный код C#, чтобы извлечь границу из определенных страниц или областей в документе PDF. Манипулируя`doc.Pages` Собирая и указывая пользовательские критерии, вы можете выбрать извлечение границы из определенных страниц или областей интереса.

#### В: Как настроить формат и качество выходного изображения?

 A: В предоставленном коде C# извлеченная граница сохраняется как изображение PNG. Если вы хотите изменить формат выходного изображения, вы можете изменить`ImageFormat.Png` параметр в`bitmap.Save` метод в другие поддерживаемые форматы изображений, такие как JPEG, BMP или GIF. Кроме того, вы можете настроить качество изображения или параметры сжатия в соответствии с вашими требованиями.

#### В: Какие еще операции я могу выполнить с извлеченной границей?

A: После того, как вы извлекли границу как изображение, вы можете дополнительно обработать его с помощью библиотек или алгоритмов обработки изображений. Вы можете проанализировать изображение, применить фильтры изображения, обнаружить шаблоны или выполнить OCR (оптическое распознавание символов) для извлечения текста из изображения, если это необходимо.

#### В: Существуют ли какие-либо ограничения или соображения при извлечении границ из сложных PDF-документов?

A: Процесс извлечения может различаться в зависимости от сложности документа PDF. Сложные PDF-файлы с несколькими слоями, прозрачностью или сложной графикой могут потребовать дополнительной обработки или корректировки для точного извлечения границы. Важно тщательно протестировать процесс извлечения на различных документах PDF, чтобы обеспечить надежные результаты.