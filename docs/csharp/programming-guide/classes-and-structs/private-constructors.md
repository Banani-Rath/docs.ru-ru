---
title: "Закрытые конструкторы (Руководство по программированию на C#) | Microsoft Docs"
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
  - "C# - язык, закрытые конструкторы"
  - "закрытые конструкторы [C#]"
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Закрытые конструкторы (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Закрытый конструктор — это особый конструктор экземпляров.  Обычно он используется в классах, содержащих только статические элементы.  Если в классе один или несколько закрытых конструкторов и ни одного открытого конструктора, то прочие классы \(за исключением вложенных классов\) не смогут создавать экземпляры этого класса.  Примеры.  
  
 [!CODE [csProgGuideObjects#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#11)]  
  
 Объявление пустого конструктора запрещает автоматическое создание конструктора по умолчанию.  Обратите внимание, что если не использовать с конструктором модификатор доступа, то по умолчанию он все равно будет закрытым.  Однако обычно используется модификатор [private](../../../csharp/language-reference/keywords/private.md), чтобы ясно обозначить невозможность создания экземпляров данного класса.  
  
 Закрытые конструкторы используются, чтобы не допустить создание экземпляров класса при отсутствии полей или методов экземпляра, например для класса <xref:System.Math>, или когда осуществляется вызов метода для получения экземпляра класса.  Если все методы в классе являются статическими, имеет смысл сделать статическим весь класс.  Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## Пример  
 Ниже приведен пример класса с закрытым конструктором.  
  
 [!CODE [csProgGuideObjects#12](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#12)]  
  
 Обратите внимание, что если снять комментарий со следующего оператора в примере, возникнет ошибка, поскольку конструктор недоступен из\-за уровня защиты:  
  
 [!CODE [csProgGuideObjects#13](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#13)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Деструкторы](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [закрытый](../../../csharp/language-reference/keywords/private.md)   
 [public](../../../csharp/language-reference/keywords/public.md)