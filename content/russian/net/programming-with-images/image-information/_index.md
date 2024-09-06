---
title: Информация об изображении в PDF-файле
linktitle: Информация об изображении в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Извлеките информацию об изображении из файла PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 160
url: /ru/net/programming-with-images/image-information/
---
Это руководство шаг за шагом проведет вас по извлечению информации об изображениях в файле PDF с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие шаги:

## Шаг 1: Определите каталог документов

 Убедитесь, что вы указали правильный каталог документа. Заменить`"YOUR DOCUMENT DIRECTORY"` в коде укажите путь к каталогу, где находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите исходный PDF-файл.

 На этом этапе мы загрузим исходный PDF-файл с помощью`Document` класс Aspose.PDF. Используйте`Document` конструктор и передайте путь к PDF-документу.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Шаг 3: Установите разрешение по умолчанию

На этом шаге мы установим разрешение по умолчанию для изображений. В примере разрешение по умолчанию установлено на 72.

```csharp
int defaultResolution = 72;
```

## Шаг 4: Инициализация объектов и счетчиков

На этом этапе мы инициализируем объекты и счетчики, необходимые для получения информации об изображении.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Шаг 5: Перебирайте операторы на первой странице документа.

На этом этапе мы рассмотрим операторов на первой странице документа, чтобы определить операции, связанные с изображениями.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Шаг 6: Управление операторами и извлечение информации об изображениях

На этом этапе мы будем управлять различными типами операторов и извлекать информацию об изображениях.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Обработка операций GSave и GRestore для преобразований
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Обработка операции ConcatenateMatrix для преобразований
else if (opCtm != null)
{
     // Применить матрицу преобразования
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Выполнение операции Do для изображений
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Получить изображение
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Получить размеры изображения
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Рассчитайте разрешение на основе информации выше.
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Отображение информации об изображении
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Пример исходного кода для информации об изображении с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузите исходный PDF-файл
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Определите разрешение изображения по умолчанию
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Определить объект списка массивов, который будет содержать имена изображений.
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Вставьте объект в стек
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Получить всех операторов на первой странице документа
foreach (Operator op in doc.Pages[1].Contents)
{
	// Используйте операторы GSave/GRestore для возврата преобразований к ранее установленным значениям.
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Создайте объект ConcatenateMatrix, поскольку он определяет текущую матрицу преобразования.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Оператор Create Do, который рисует объекты из ресурсов. Рисует объекты Form и объекты Image
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Сохранить предыдущее состояние и поместить текущее состояние наверх стека
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Удалить текущее состояние и восстановить предыдущее
		graphicsState.Pop();
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
		continue;
	}
	else if (opDo != null)
	{
		// В случае, если это оператор рисования изображения
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Создать объект XImage для хранения изображений первой страницы PDF-файла.
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Получить размеры изображения
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Получить информацию о высоте и ширине изображения
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Вычислить разрешение на основе вышеуказанной информации
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Отображение информации о размерах и разрешении каждого изображения
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Заключение

Поздравляем! Теперь вы узнали, как извлекать информацию об изображении из файла PDF с помощью Aspose.PDF для .NET. Вы можете использовать эту информацию для различных задач обработки изображений в своих приложениях.

### Часто задаваемые вопросы об информации об изображении в файле PDF

#### В: Какова цель извлечения информации об изображении из PDF-документа с помощью Aspose.PDF для .NET?

A: Извлечение информации об изображении из документа PDF дает представление о размерах, разрешении и других атрибутах изображений в документе. Эта информация может использоваться для задач обработки, анализа или оптимизации изображений.

#### В: Как Aspose.PDF for .NET помогает извлекать информацию об изображении из PDF-документа?

A: Aspose.PDF для .NET предоставляет инструменты для доступа и анализа содержимого PDF-документа, включая его изображения. Предоставленный код демонстрирует, как извлекать и отображать информацию об изображениях с помощью различных операторов.

#### В: Какую информацию об изображении можно извлечь с помощью этого метода?

A: Этот метод позволяет извлекать и отображать такую информацию, как масштабированные размеры, разрешение и названия изображений в документе PDF.

#### В: Как код идентифицирует и обрабатывает операторы, связанные с изображениями, в документе PDF?

A: Код выполняет итерацию по операторам на указанной странице документа PDF. Он идентифицирует и обрабатывает операторы, связанные с операциями с изображениями, преобразованиями и рендерингом.

#### В: Каково значение разрешения по умолчанию и как оно используется в коде?

A: Разрешение по умолчанию используется как точка отсчета для расчета фактического разрешения изображений. Код вычисляет разрешение каждого изображения на основе его размеров и настройки разрешения по умолчанию.

#### В: Как можно использовать извлеченную информацию об изображении в реальных сценариях?

A: Извлеченную информацию об изображении можно использовать для таких задач, как оценка качества изображения, оптимизация изображения, создание эскизов изображений и упрощение процессов принятия решений, связанных с изображениями.

#### В: Могу ли я изменить код, чтобы извлечь дополнительные атрибуты, связанные с изображением?

A: Да, вы можете настроить код для извлечения дополнительных атрибутов изображений, таких как цветовое пространство, глубина пикселей или тип изображения.

#### В: Является ли процесс извлечения информации из изображений ресурсоемким или занимает много времени?

A: Процесс извлечения информации об изображении эффективен и оптимизирован для производительности, обеспечивая минимальное влияние на использование ресурсов и время обработки.

#### В: Какую пользу могут получить разработчики от идентификации и извлечения информации об изображениях из PDF-документов?

A: Разработчики могут получить представление о характеристиках изображений в PDF-документах, что позволит им принимать обоснованные решения относительно манипулирования изображениями, их обработки и оптимизации.

#### В: Можно ли использовать этот метод для пакетной обработки PDF-документов, содержащих изображения?

A: Да, этот метод можно расширить для пакетной обработки путем итерации по нескольким страницам или документам, извлечения информации об изображениях и выполнения задач, связанных с изображениями.