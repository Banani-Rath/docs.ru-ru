---
title: "Практическое руководство. Объявление и использование свойств чтения и записи (руководство по программированию на C#) | Microsoft Docs"
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
  - "метод доступа get [C#], объявление свойств"
  - "set - метод доступа [C#]"
  - "свойства [C#], объявление"
  - "свойства чтения/записи [C#]"
  - "методы доступа [C#], объявление свойств с помощью"
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Объявление и использование свойств чтения и записи (руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Свойства обеспечивают удобную работу с открытыми членами данных без риска, с которым связан незащищенный, неконтролируемый и непроверяемый доступ к данным объекта.  Это достигается с помощью *методов доступа*: особых методов, которые назначают и извлекают значения из базового члена данных.  Метод доступа [set](../../../csharp/language-reference/keywords/set.md) обеспечивает назначение членов данных, а метод [get](../../../csharp/language-reference/keywords/get.md) извлекает значения членов данных.  
  
 В этом примере показан простой класс `Person`, имеющий два свойства: `Name`\(string\) и `Age` \(int\).  Оба свойства предоставляют методы доступа `get` и `set`, поэтому они считаются свойствами чтения и записи.  
  
## Пример  
 [!CODE [csProgGuideObjects#33](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#33)]  
  
## Отказоустойчивость  
 В предыдущем примере свойства `Name` и `Age` являются [открытыми](../../../csharp/language-reference/keywords/public.md) и содержат методы доступа `get` и `set`.  При этом любой объект может выполнять чтение и запись данных свойств.  Однако иногда рекомендуется исключить один из методов доступа.  Если, например, будет опущен метод доступа `set`, средство станет доступным только для чтения.  
  
 [!CODE [csProgGuideObjects#87](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#87)]  
  
 Можно также сделать один метод доступа открытым, а другой — закрытым или защищенным.  Дополнительные сведения см. в разделе [Простота использования асимметричных методов доступа\)](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
 Объявленные свойства могут использоваться в качестве полей класса.  Это приводит к более естественному синтаксису, где выполняется получение и установка значения свойства, как в следующих операторах.  
  
 [!CODE [csProgGuideObjects#35](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#35)]  
  
 Обратите внимание, что в свойстве метода `set` доступна особая переменная `value`.  Эта переменная содержит значение, заданное пользователем, например:  
  
 [!CODE [csProgGuideObjects#36](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#36)]  
  
 Обратите внимание на чистый синтаксис для увеличения значения свойства `Age` объекта `Person`.  
  
 [!CODE [csProgGuideObjects#37](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#37)]  
  
 Если для моделирования свойств использовались отдельные методы `set` и `get`, эквивалентный код может выглядеть следующим образом.  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 В этом примере метод `ToString` переопределен.  
  
 [!CODE [csProgGuideObjects#38](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#38)]  
  
 Обратите внимание, что `ToString` не используется явно в программе.  Он вызывается по умолчанию вызовами `WriteLine`.  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)