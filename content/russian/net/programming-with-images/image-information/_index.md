---
title: Информация об изображении в PDF-файле
linktitle: Информация об изображении в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Извлеките информацию об изображении в файл PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 160
url: /ru/net/programming-with-images/image-information/
---
В этом руководстве шаг за шагом вы узнаете, как извлечь информацию об изображениях в файл PDF с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1. Определите каталог документов.

 Обязательно установите правильный каталог документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде укажите путь к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходный PDF-файл.

 На этом этапе мы загрузим исходный PDF-файл, используя`Document` класс Aspose.PDF. Использовать`Document` конструктор и передайте путь к PDF-документу.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Шаг 3. Установите разрешение по умолчанию

На этом этапе мы установим разрешение по умолчанию для изображений. В примере разрешение по умолчанию установлено на 72.

```csharp
int defaultResolution = 72;
```

## Шаг 4. Инициализация объектов и счетчиков

На этом этапе мы инициализируем объекты и счетчики, необходимые для получения информации об изображении.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Шаг 5. Циклическое переключение операторов на первой странице документа.

На этом этапе мы рассмотрим операторы на первой странице документа, чтобы определить операции, связанные с изображениями.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Шаг 6. Управление операторами и извлечение информации об изображении

На этом этапе мы будем управлять различными типами операторов и извлекать информацию об изображениях.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Обработка операций GSave и GRestore для преобразований.
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
     // Примените матрицу преобразования
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
// Обработка операции Do для изображений
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Получить изображение
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Получить размеры изображения
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Рассчитайте разрешение на основе приведенной выше информации.
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
// Определите разрешение по умолчанию для изображения
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Определите объект списка массивов, который будет содержать имена изображений.
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Вставьте объект в стопку
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Получить все операторы на первой странице документа
foreach (Operator op in doc.Pages[1].Contents)
{
	// Используйте операторы GSave/GResstore, чтобы вернуть преобразования к ранее установленным значениям.
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Создайте экземпляр объекта ConcatenateMatrix, поскольку он определяет текущую матрицу преобразования.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Создайте оператор Do, который извлекает объекты из ресурсов. Он рисует объекты формы и объекты изображения.
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Сохраните предыдущее состояние и поместите текущее состояние в начало стека.
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Выбросить текущее состояние и восстановить предыдущее
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
		// Умножьте текущую матрицу на матрицу состояний.
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// В случае, если это оператор рисования изображения
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Создайте объект XImage для хранения изображений первой страницы PDF.
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Получить размеры изображения
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Получить информацию о высоте и ширине изображения
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Вычисление разрешения на основе приведенной выше информации
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Отображение информации о размере и разрешении каждого изображения.
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Заключение

Поздравляем! Теперь вы узнали, как извлечь информацию об изображении в файл PDF с помощью Aspose.PDF для .NET. Вы можете использовать эту информацию для различных задач обработки изображений в своих приложениях.

### Часто задаваемые вопросы по информации об изображениях в PDF-файле

#### Вопрос: Какова цель извлечения информации об изображении из PDF-документа с помощью Aspose.PDF для .NET?

О: Извлечение информации об изображении из PDF-документа дает представление о размерах, разрешении и других атрибутах изображений в документе. Эту информацию можно использовать для задач обработки, анализа или оптимизации изображений.

#### Вопрос: Как Aspose.PDF for .NET помогает извлекать информацию об изображении из PDF-документа?

О: Aspose.PDF для .NET предоставляет инструменты для доступа и анализа содержимого PDF-документа, включая его изображения. Предоставленный код демонстрирует, как извлекать и отображать информацию об изображении с помощью различных операторов.

#### Вопрос: Какую информацию об изображении можно извлечь с помощью этого метода?

О: Этот метод позволяет извлекать и отображать такую информацию, как масштабированные размеры, разрешение и имена изображений в PDF-документе.

#### Вопрос: Как код идентифицирует и обрабатывает операторы, связанные с изображениями, в PDF-документе?

О: Код выполняет итерацию операторов на указанной странице PDF-документа. Он идентифицирует и обрабатывает операторы, связанные с операциями с изображениями, преобразованиями и рендерингом.

#### Вопрос: Каково значение разрешения по умолчанию и как оно используется в коде?

О: Разрешение по умолчанию используется в качестве ориентира для расчета фактического разрешения изображений. Код вычисляет разрешение каждого изображения на основе его размеров и настроек разрешения по умолчанию.

#### Вопрос: Как можно использовать извлеченную информацию об изображении в реальных сценариях?

Ответ: Извлеченная информация об изображении может использоваться для таких задач, как оценка качества изображения, оптимизация изображения, создание миниатюр изображений и упрощение процессов принятия решений, связанных с изображением.

#### Вопрос: Могу ли я изменить код для извлечения дополнительных атрибутов, связанных с изображением?

О: Да, вы можете настроить код для извлечения дополнительных атрибутов изображений, таких как цветовое пространство, глубина пикселей или тип изображения.

#### Вопрос: Является ли процесс извлечения информации об изображении ресурсоемким или трудоемким?

Ответ: Процесс извлечения информации об изображении эффективен и оптимизирован по производительности, обеспечивая минимальное влияние на использование ресурсов и время обработки.

#### Вопрос: Какую пользу разработчики могут получить от идентификации и извлечения информации об изображениях из PDF-документов?

О: Разработчики могут получить представление о характеристиках изображений в документах PDF, что позволит им принимать обоснованные решения относительно манипулирования, обработки и оптимизации изображений.

#### Вопрос: Можно ли использовать этот метод для пакетной обработки PDF-документов, содержащих изображения?

О: Да, этот метод можно расширить для пакетной обработки, проходя по нескольким страницам или документам, извлекая информацию об изображении и выполняя задачи, связанные с изображениями.