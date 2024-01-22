---
title: Botões de opção horizontal e vertical
linktitle: Botões de opção horizontal e vertical
second_title: Referência da API Aspose.PDF para .NET
description: Crie facilmente botões de opção horizontais e verticais em seus documentos PDF com Aspose.PDF for .NET.
type: docs
weight: 180
url: /pt/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
Neste tutorial, mostraremos como criar botões de opção organizados horizontal e verticalmente em um documento PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo neste processo.

## Etapa 1: Preparação

Certifique-se de importar as bibliotecas necessárias e definir o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregue o documento

Carregue o documento PDF existente:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Etapa 3: personalizar as opções do botão de opção

Personalize as opções do botão de opção definindo as seguintes propriedades:

```csharp
formEditor. RadioGap = 4; // Distância entre duas opções de botão de opção
formEditor. RadioHoriz = true; //Layout horizontal de botões de opção
formEditor.RadioButtonItemSize = 20; // Tamanho dos botões de opção
formEditor.Facade.BorderWidth = 1; // Largura da borda do botão de opção
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Cor da borda do botão de opção
```

## Etapa 4: adicionar botões de opção horizontais

Adicione botões de opção organizados horizontalmente especificando as opções e a posição do campo:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Etapa 5: adicionar botões de opção verticais

Adicione botões de opção organizados verticalmente especificando as opções e a posição do campo:

```csharp
formEditor. RadioHoriz = false; // Layout vertical de botões de opção
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Etapa 6: salve o documento

Salve o documento PDF modificado:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Exemplo de código-fonte para botões de opção horizontal e vertical usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carregue o documento salvo anteriormente
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap é a distância entre duas opções de botão de opção.
	formEditor.RadioGap = 4;
	// Adicionar botão de opção horizontal
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize se for o tamanho do item do botão de opção.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Adicione outro botão de opção situado verticalmente
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Salve o documento PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão

Neste tutorial, aprendemos como criar botões de opção organizados horizontal e verticalmente em um documento PDF usando Aspose.PDF for .NET. Seguindo essas etapas, você pode personalizar facilmente o layout dos botões de opção e adicioná-los aos seus documentos PDF usando Aspose.PDF.

### Perguntas frequentes

#### P: O que são botões de opção dispostos horizontal e verticalmente em um documento PDF?

R: Os botões de opção dispostos horizontal e verticalmente em um documento PDF referem-se à orientação do layout das opções dos botões de opção. O layout horizontal coloca as opções dos botões de opção lado a lado, permitindo que os usuários façam uma seleção da esquerda para a direita. O layout vertical, por outro lado, empilha as opções dos botões de opção umas sobre as outras, permitindo que os usuários façam uma seleção de cima para baixo.

#### P: Como posso personalizar a aparência das opções dos botões de opção no Aspose.PDF for .NET?

R: Você pode personalizar a aparência das opções dos botões de opção no Aspose.PDF for .NET ajustando várias propriedades. A API fornece opções para definir a distância entre duas opções de botão de opção (`RadioGap`), a orientação do layout (`RadioHoriz`), o tamanho dos itens do botão de opção (`RadioButtonItemSize`), a largura da borda e a cor dos botões de opção e muito mais.

#### P: Posso adicionar botões de opção horizontais e verticais ao mesmo documento PDF?

R: Sim, você pode adicionar botões de opção horizontais e verticais ao mesmo documento PDF usando Aspose.PDF for .NET. O exemplo de código-fonte fornecido no tutorial demonstra como primeiro adicionar botões de opção organizados horizontalmente e, em seguida, adicionar outro conjunto de botões de opção dispostos verticalmente ao mesmo documento PDF.

#### P: Posso definir diferentes opções de botões de opção para cada grupo de botões de opção?

 R: Sim, você pode definir diferentes opções de botões de opção para cada grupo de botões de opção. Cada grupo deve ter um único`RadioButtonField` objeto, e o`RadioButtonOptionField` os objetos dentro de cada grupo devem compartilhar a mesma página e nomes exclusivos para suas opções. Isso garante que os botões de opção dentro de cada grupo funcionem corretamente e que as seleções sejam mutuamente exclusivas.

#### P: As configurações de layout e aparência dos botões de opção são suportadas em todos os visualizadores e aplicativos de PDF?

R: Sim, as configurações de layout e aparência dos botões de opção são suportadas em todos os visualizadores e aplicativos de PDF compatíveis com o padrão. A especificação PDF define botões de opção e seus diversos atributos, tornando-os universalmente reconhecidos no formato PDF. No entanto, é essencial testar a aparência e o comportamento dos botões de opção em diferentes visualizadores de PDF para garantir uma renderização consistente em diversas plataformas.