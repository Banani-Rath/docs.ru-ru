---
title: "override (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "override"
  - "override_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "override - ключевое слово [C#]"
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# override (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Модификатор `override` требуется для расширения или изменения абстрактной или виртуальной реализации унаследованного метода, свойства, индексатора или события.  
  
## Пример  
 В этом примере класс `Square` должен предоставить переопределенную реализацию `Area`, поскольку `Area` является унаследованным от абстрактного класса `ShapesClass`.  
  
 [!CODE [csrefKeywordsModifiers#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#1)]  
  
 Метод `override` предоставляет новую реализацию члена, унаследованного от базового класса.  Метод, переопределенный объявлением `override`, называется переопределенным базовым методом.  Переопределенный базовый метод должен иметь ту же сигнатуру, что и метод `override`.  Дополнительные сведения о наследовании см. в разделе [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Невиртуальный или статический метод нельзя переопределить.  Переопределенный базовый метод должен иметь тип `virtual`, `abstract` или `override`.  
  
 Объявление `override` не может изменить доступность метода `virtual`.  Методы `override` и `virtual` должны иметь одинаковый [модификатор уровня доступа](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Модификаторы `new`, `static` и `virtual` нельзя использовать для изменения метода `override`.  
  
 Переопределяющее объявление свойства должна задавать такие же модификатор уровня доступа, тип и имя, которые имеются у унаследованного свойства, а переопределенное свойство должно иметь тип `virtual`, `abstract` или `override`.  
  
 Дополнительные сведения об использовании ключевого слова `override` см. в разделах [Управление версиями с помощью ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) и [Аспекты использованию ключевых слов "Override" и "New"](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## Пример  
 В этом примере определяется базовый класс с именем `Employee` и производный класс с именем `SalesEmployee`.  Класс `SalesEmployee` включает дополнительное свойство `salesbonus`, для использования которого переопределяется метод `CalculatePay`.  
  
 [!CODE [csrefKeywordsModifiers#9](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#9)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)   
 [виртуальные](../../../csharp/language-reference/keywords/virtual.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [Полиморфизм](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)