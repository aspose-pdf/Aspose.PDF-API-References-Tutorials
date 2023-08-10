---
title: Получить ширину текста динамически
linktitle: Получить ширину текста динамически
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как динамически получить ширину текста с помощью Aspose.PDF для .NET.
type: docs
weight: 220
url: /ru/net/programming-with-text/get-width-of-text-dynamically/
---

В этом руководстве мы объясним, как использовать Aspose.PDF для .NET для динамического измерения ширины текста в C#. Это может быть полезно, когда вам нужно определить размер текстовой строки перед ее визуализацией в документе PDF. Мы шаг за шагом проведем вас через предоставленный исходный код C#.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Visual Studio или любая другая среда разработки C#.

## Шаг 1. Установите каталог документов

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"`с указанием пути к каталогу, в котором находятся ваши документы. Это будет использоваться для хранения любых сгенерированных файлов PDF.

## Шаг 2: Найдите шрифт

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
```

 Приведенный выше код находит шрифт Arial, используя`FindFont` метод из`FontRepository` сорт. Если вы хотите использовать другой шрифт, замените`"Arial"` с желаемым названием шрифта.

## Шаг 3: Установите состояние текста

```csharp
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
```

 Здесь мы создаем новый`TextState` объекта и установить его свойства. Присваиваем ранее найденный шрифт (`font`) и установите размер шрифта 14. При необходимости отрегулируйте размер шрифта.

## Шаг 4: Измерьте ширину текста

```csharp
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```

В приведенном выше коде показано, как измерить ширину текста, используя шрифт напрямую (`font.MeasureString`) и состояние текста (`ts.MeasureString`). Он включает в себя некоторые проверочные проверки для обеспечения точности измерений.

### Пример исходного кода для динамического получения ширины текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```


## Заключение

Вы узнали, как использовать Aspose.PDF для .NET для динамического измерения ширины текста в C#. Следуя шагам, описанным в этом руководстве, вы сможете точно определить ширину текстовых строк перед их визуализацией в документе PDF.