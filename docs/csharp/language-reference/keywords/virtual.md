---
title: "virtual (Справочник по C#) | Microsoft Docs"
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
  - "virtual_CSharpKeyword"
  - "virtual"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "virtual - ключевое слово [C#]"
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# virtual (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `virtual` используется для изменения объявлений методов, свойств, индексаторов и событий и разрешения их переопределения в производном классе.  Например, этот метод может быть переопределен любым производным классом:  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 Реализацию виртуального члена можно изменить путем [переопределения члена](../../../csharp/language-reference/keywords/override.md) в производном классе.  Дополнительные сведения об использовании ключевого слова `virtual` см. в разделах [Управление версиями с помощью ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) и [Использование ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## Заметки  
 При вызове виртуального метода тип времени выполнения объекта проверяется на переопределение члена.  Вызывается переопределение члена в самом дальнем классе. Это может быть исходный член, если никакой производный класс не выполнял переопределение этого члена.  
  
 По умолчанию методы не являются виртуальными.  Такой метод нельзя переопределить.  
  
 Модификатор `virtual` нельзя использовать с модификаторами `static`, `abstract, private` или `override`.  В следующем примере показано виртуальное свойство.  
  
 [!CODE [csrefKeywordsModifiers#26](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#26)]  
  
 Действие виртуальных свойств аналогично абстрактным методам, за исключением отличий в синтаксисе объявлений и вызовов.  
  
-   Использование модификатора `virtual` в статическом свойстве является недопустимым.  
  
-   Виртуальное наследуемое свойство может быть переопределено в производном классе путем включения объявления свойства, которое использует модификатор `override`.  
  
## Пример  
 В этом примере класс `Shape` содержит две координаты `x`, `y` и виртуальный метод `Area()`.  Различные классы фигур, такие как `Circle`, `Cylinder` и `Sphere`, наследуют класс `Shape`, и для каждой фигуры вычисляется площадь поверхности.  Каждый производный класс обладает собственной реализацией переопределения метода `Area()`.  
  
 Обратите внимание, что наследуемые классы `Circle`"  `Sphere`и  `Cylinder` все конструкторы использования, которые инициализируют базовый класс, как показано в следующем объявлении.  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 Следующая программа вычисляет и отображает соответствующую область для каждой диаграммы путем вызова соответствующую реализацию `Area()` метод в соответствии с объектом, связанного с методом.  
  
 [!CODE [csrefKeywordsModifiers#23](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#23)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Полиморфизм](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [new](../../../csharp/language-reference/keywords/new.md)