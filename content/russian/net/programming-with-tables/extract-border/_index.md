---
title: Извлечь границу из PDF-файла
linktitle: Извлечь границу из PDF-файла
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как извлечь границу в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 80
url: /ru/net/programming-with-tables/extract-border/
---
В этом уроке мы узнаем, как извлечь границу в PDF-файле с помощью Aspose.PDF для .NET. Мы объясним исходный код на C# шаг за шагом. В конце этого урока вы узнаете, как извлечь рамку из PDF-документа и сохранить ее как изображение. Давайте начнем!

## Шаг 1. Настройка среды
Сначала убедитесь, что вы настроили свою среду разработки C# с помощью Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2. Загрузка PDF-документа
На этом этапе мы загружаем PDF-документ из указанного файла.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Обязательно замените «КАТАЛОГ ВАШЕГО ДОКУМЕНТА» на фактический каталог, в котором находится ваш PDF-файл.

## Шаг 3: Извлечение краев
Мы извлечем границу из PDF-документа, перебирая операции, содержащиеся в документе.

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
     // Обрабатывать все операции с контентом
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Проверьте тип операции
         // ...
         // Добавьте код для обработки каждой операции
     }
}
```

 Мы создаем`graphicsState` стек для хранения графических состояний, растровое изображение для захвата извлеченной границы,`GraphicsPath` объект для хранения путей рисования и другие переменные для отслеживания состояния и цветов.

## Шаг 4: Обработка транзакции
На этом этапе мы обрабатываем каждую операцию документа для извлечения границы.

```csharp
// Проверьте тип операции
if (opSaveState != null)
{
     // Сохраните предыдущее состояние и поместите текущее состояние на вершину стека.
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

     // Умножьте текущую матрицу на матрицу состояний
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
     // Обработка рисования линии
     // ...
     // Добавьте код для обработки рисования линии
}
// ...
// Добавьте else if блоки для других операций
```

Мы проверяем тип операции с помощью условий и запускаем соответствующий код для каждой операции.

## Шаг 5: Резервное изображение
Наконец, мы сохраняем растровое изображение, содержащее извлеченную рамку, в указанный файл.

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
// Значение матрицы ctm по умолчанию — 1,0,0,1,0,0.
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Система координат System.Drawing основана на левом верхнем углу, а система координат PDF — на нижнем левом углу, поэтому нам нужно применить матрицу инверсии.
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
			//Сохраните предыдущее состояние и поместите текущее состояние в начало стека.
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Выбросить текущее состояние и восстановить предыдущее
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

			// Умножьте текущую матрицу на матрицу состояний.
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
В этом уроке мы узнали, как извлечь рамку из PDF-документа с помощью Aspose.PDF для .NET. Вы можете использовать это пошаговое руководство, чтобы извлечь рамку из других PDF-документов.

### Часто задаваемые вопросы по извлечению границы в PDF-файле

#### Вопрос: Какова цель извлечения границы из PDF-файла?

О: Извлечение границы из PDF-файла может быть полезно для различных целей. Он позволяет изолировать и анализировать структурные элементы документа, такие как таблицы, диаграммы или графические элементы. Вы можете использовать извлеченную рамку, чтобы определить макет, размеры и расположение содержимого в PDF-документе.

#### Вопрос: Могу ли я извлечь рамку из определенных страниц или областей PDF-документа?

О: Да, вы можете изменить предоставленный исходный код C#, чтобы извлечь границу из определенных страниц или областей PDF-документа. Манипулируя`doc.Pages` сбора и указания пользовательских критериев, вы можете выбрать выделение границы из определенных страниц или областей, представляющих интерес.

#### Вопрос: Как настроить формат и качество выходного изображения?

 О: В предоставленном коде C# извлеченная граница сохраняется как изображение PNG. Если вы хотите изменить формат выходного изображения, вы можете изменить`ImageFormat.Png` параметр в`bitmap.Save` в другие поддерживаемые форматы изображений, такие как JPEG, BMP или GIF. Кроме того, вы можете настроить качество изображения или параметры сжатия в соответствии с вашими требованиями.

#### Вопрос: Какие еще операции можно выполнить с выделенной границей?

О: После того как вы извлекли границу в виде изображения, вы можете дополнительно обработать ее с помощью библиотек или алгоритмов обработки изображений. Вы можете анализировать изображение, применять фильтры изображений, обнаруживать шаблоны или выполнять OCR (оптическое распознавание символов), чтобы при необходимости извлечь текст из изображения.

#### Вопрос: Существуют ли какие-либо ограничения или соображения при извлечении границ из сложных PDF-документов?

О: Процесс извлечения может различаться в зависимости от сложности PDF-документа. Сложные PDF-файлы с несколькими слоями, прозрачностью или расширенной графикой могут потребовать дополнительной обработки или корректировок для точного выделения границы. Очень важно тщательно протестировать процесс извлечения различных PDF-документов, чтобы обеспечить надежные результаты.