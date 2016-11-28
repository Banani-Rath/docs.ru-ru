---
title: "Практическое руководство. Объявление констант в C# | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, константы"
  - "константы [C#]"
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Объявление констант в C#
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Константы — это поля, значения которых устанавливаются во время компиляции и не изменяются.  Использование констант позволяет оперировать значимыми именами числовых литералов для особых значений.  
  
> [!NOTE]
>  В C\# нельзя использовать директиву предварительной обработки [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) для определения переменных таким же образом, как это обычно делается в C и C\+\+.  
  
 Чтобы определить значения переменных интегральных типов \(`int`, `byte` и т.д.\), следует использовать перечисленный тип.  Дополнительные сведения см. в разделе [перечисление](../../../csharp/language-reference/keywords/enum.md).  
  
 Чтобы определить неинтегральные константы, можно сгруппировать их в один статический класс `Constants`.  При этом будет необходимо указывать во всех ссылках на константы имя класса, как показано в следующем примере.  
  
## Пример  
 [!CODE [csProgGuideObjects#89](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#89)]  
  
 Использование имени класса помогает упростить написание кода: все разработчики, использующие константу, понимают, что она является таковой и не может быть изменена.  
  
## См. также  
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)