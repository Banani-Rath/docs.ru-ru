---
title: "abstract (Справочник по C#) | Microsoft Docs"
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
  - "abstract"
  - "abstract_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "abstract - ключевое слово [C#]"
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# abstract (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Модификатор `abstract` указывает, что реализация изменяемого объекта является неполной или отсутствует.  Модификатор abstract может использоваться с классами, методами, свойствами, индексаторами и событиями.  Модификатор `abstract` в объявлении класса указывает, что класс предназначен только для использования в качестве базового класса для других классов.  Члены, помеченные как абстрактные или включенные в абстрактный класс, должны быть реализованы с помощью классов, производных от абстрактных классов.  
  
## Пример  
 В этом примере класс `Square` должен предоставить реализацию `Area`, поскольку он является производным `ShapesClass`.  
  
 [!CODE [csrefKeywordsModifiers#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#1)]  
  
 Далее представлены возможности абстрактных классов.  
  
-   Создавать экземпляры абстрактного класса нельзя.  
  
-   Абстрактные классы могут содержать абстрактные методы и методы доступа.  
  
-   Абстрактный класс с модификатором [запечатанные](../../../csharp/language-reference/keywords/sealed.md) изменить нельзя, поскольку эти два модификатора имеют взаимоисключающие значения.  Модификатор `sealed` запрещает наследовать классу, в то время как модификатор `abstract` указывает, что класс обязан иметь производные классы.  
  
-   Неабстрактный класс, являющийся производным от абстрактного, должен содержать фактические реализации всех наследуемых абстрактных методов и методов доступа.  
  
 Чтобы указать отсутствие реализации в методе или свойстве, воспользуйтесь модификатором `abstract` в объявлении метода или свойства.  
  
 Далее представлены возможности абстрактных методов.  
  
-   Абстрактный метод является неявным виртуальным методом.  
  
-   Объявления абстрактных методов допускаются только в абстрактных классах.  
  
-   Поскольку объявление абстрактного метода не предоставляет фактической реализации, тело метода отсутствует; объявление метода просто заканчивается двоеточием, а после сигнатуры ставить фигурные скобки \({ }\) не нужно.  Примеры.  
  
    ```  
    public abstract void MyMethod();  
    ```  
  
     Реализация предоставляется методом переопределения [override](../../../csharp/language-reference/keywords/override.md), который является членом неабстрактного класса.  
  
-   Использование [статических](../../../csharp/language-reference/keywords/static.md) или [виртуальных](../../../csharp/language-reference/keywords/virtual.md) модификаторов в объявлении абстрактного метода является недопустимым.  
  
 Действие абстрактных свойств аналогично абстрактным методам, за исключением отличий в синтаксисе объявлений и вызовов.  
  
-   Использование модификатора `abstract` в статическом свойстве является недопустимым.  
  
-   Абстрактное унаследованное свойство может быть переопределено в производном классе за счет включения объявления свойства, использующего модификатор [переопределения](../../../csharp/language-reference/keywords/override.md).  
  
 Дополнительные сведения об абстрактных классах см. в разделе [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Абстрактный класс должен предоставлять реализацию для всех членов интерфейса.  
  
 Абстрактный класс, реализующий интерфейс, может отображать методы интерфейса в абстрактных методах.  Примеры.  
  
 [!CODE [csrefKeywordsModifiers#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#2)]  
  
## Пример  
 В этом примере класс `DerivedClass` является производным от абстрактного класса `BaseClass`.  Абстрактный класс содержит абстрактный метод `AbstractMethod` и два абстрактных свойства — `X` и `Y`.  
  
 [!CODE [csrefKeywordsModifiers#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#3)]  
  
 В предыдущем примере при попытке создать абстрактный класс с помощью следующего оператора  
  
```  
BaseClass bc = new BaseClass();   // Error  
```  
  
 появится сообщение об ошибке, указывающее, что компилятору не удается создать экземпляр абстрактного класса "BaseClass".  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [виртуальные](../../../csharp/language-reference/keywords/virtual.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)