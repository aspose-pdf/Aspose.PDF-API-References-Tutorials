---
title: Botões de opção horizontal e vertical
linktitle: Botões de opção horizontal e vertical
second_title: Referência da API do Aspose.PDF para .NET
description: Crie facilmente botões de opção horizontais e verticais em seus documentos PDF com Aspose.PDF para .NET.
type: docs
weight: 180
url: /pt/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
Neste tutorial, mostraremos como criar botões de rádio dispostos horizontal e verticalmente em um documento PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Carregue o documento

Carregue o documento PDF existente:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Etapa 3: personalizar opções de botão de opção

Personalize as opções dos botões de opção definindo as seguintes propriedades:

```csharp
formEditor. RadioGap = 4; // Distância entre duas opções de botão de rádio
formEditor. RadioHoriz = true; //Layout horizontal de botões de opção
formEditor.RadioButtonItemSize = 20; // Tamanho dos botões de opção
formEditor.Facade.BorderWidth = 1; // Largura da borda do botão de opção
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Cor da borda do botão de opção
```

## Etapa 4: Adicionar botões de opção horizontais

Adicione botões de opção organizados horizontalmente especificando as opções e a posição do campo:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Etapa 5: adicione botões de opção verticais

Adicione botões de opção organizados verticalmente especificando as opções e a posição do campo:

```csharp
formEditor. RadioHoriz = false; // Layout vertical dos botões de opção
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Etapa 6: Salve o documento

Salve o documento PDF modificado:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Exemplo de código-fonte para botões de opção horizontais e verticais usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carregue o documento salvo anteriormente
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap é a distância entre duas opções de botões de rádio.
	formEditor.RadioGap = 4;
	// Adicionar botão de opção horizontal
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize se o tamanho do item do botão de opção.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Adicionar outro botão de opção situado verticalmente
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Salvar o documento PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão

Neste tutorial, aprendemos como criar botões de opção dispostos horizontal e verticalmente em um documento PDF usando o Aspose.PDF para .NET. Seguindo essas etapas, você pode personalizar facilmente o layout dos botões de opção e adicioná-los aos seus documentos PDF usando o Aspose.PDF.

### Perguntas frequentes

#### P: O que são botões de opção dispostos horizontalmente e verticalmente em um documento PDF?

R: Botões de opção dispostos horizontal e verticalmente em um documento PDF referem-se à orientação do layout das opções de botões de opção. O layout horizontal coloca as opções de botões de opção lado a lado, permitindo que os usuários façam uma seleção da esquerda para a direita. O layout vertical, por outro lado, empilha as opções de botões de opção umas sobre as outras, permitindo que os usuários façam uma seleção de cima para baixo.

#### P: Como posso personalizar a aparência das opções de botões de opção no Aspose.PDF para .NET?

R: Você pode personalizar a aparência das opções de botões de rádio no Aspose.PDF para .NET ajustando várias propriedades. A API fornece opções para definir a distância entre duas opções de botões de rádio (`RadioGap`), a orientação do layout (`RadioHoriz`), o tamanho dos itens do botão de opção (`RadioButtonItemSize`), a largura da borda e a cor dos botões de opção e muito mais.

#### P: Posso adicionar botões de opção horizontais e verticais ao mesmo documento PDF?

R: Sim, você pode adicionar botões de opção horizontais e verticais ao mesmo documento PDF usando o Aspose.PDF para .NET. O código-fonte de exemplo fornecido no tutorial demonstra como primeiro adicionar botões de opção dispostos horizontalmente e, em seguida, adicionar outro conjunto de botões de opção dispostos verticalmente ao mesmo documento PDF.

#### P: Posso definir opções diferentes de botões de opção para cada grupo de botões de opção?

 R: Sim, você pode definir diferentes opções de botões de rádio para cada grupo de botões de rádio. Cada grupo deve ter um único`RadioButtonField` objeto, e o`RadioButtonOptionField` objetos dentro de cada grupo devem compartilhar a mesma página e nomes exclusivos para suas opções. Isso garante que os botões de opção dentro de cada grupo funcionem corretamente, e as seleções sejam mutuamente exclusivas.

#### P: As configurações de layout e aparência dos botões de opção são suportadas em todos os aplicativos e visualizadores de PDF?

R: Sim, as configurações de layout e aparência dos botões de opção são suportadas em todos os visualizadores e aplicativos de PDF compatíveis com o padrão. A especificação PDF define botões de opção e seus vários atributos, tornando-os universalmente reconhecidos no formato PDF. No entanto, é essencial testar a aparência e o comportamento dos botões de opção em diferentes visualizadores de PDF para garantir uma renderização consistente em várias plataformas.