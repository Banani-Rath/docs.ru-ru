---
title: "Модификатор new (Справочник по C#) | Microsoft Docs"
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
  - "new modifier - ключевое слово [C#]"
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Модификатор new (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При использовании в качестве модификатора объявления ключевое слово `new` явным образом скрывает члены, унаследованные от базового класса.  При скрытии унаследованного члена его производная версия заменяет версию базового класса.  Хотя члены можно скрывать без использования модификатора `new`, в этом случае появляется предупреждение компилятора.  При использовании `new` для явного скрытия члена, предупреждение не появляется.  
  
 Чтобы скрыть унаследованный член, объявите его в производном классе с использованием такого же имени члена и измените с помощью ключевого слова `new`.  Пример:  
  
 [!CODE [csrefKeywordsOperator#8](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsOperator#8)]  
  
 В этом примере `BaseC.Invoke` скрывается с помощью `DerivedC.Invoke`.  Поле `x` не затрагивается, поскольку оно не скрыто таким же именем.  
  
 Скрытие имен через наследование принимает одну из следующих форм.  
  
-   Как правило, константы, поля, свойства и типы, которые вводятся в классе или структуре, скрывают все члены базового класса с таким же именем.  Однако существуют особые случаи.  Например, если объявить новое поле с именем `N`, чтобы сделать тип невызываемым, в то время как в базовом типе был объявлен метод `N`, новое поле не скрывает базовое объявление в синтаксисе вызова.  Подробные сведения см. в [спецификации языка C\#](http://go.microsoft.com/fwlink/?LinkId=199552) \(см. подраздел «Поиск члена» в разделе «Выражения»\).  
  
-   Метод, введенный в классе или структуре, скрывает свойства, поля и типы с тем же именем в базовом классе.  Кроме того, он также скрывает все методы базового класса, имеющие такую же сигнатуру.  
  
-   Индексатор, представленный в классе или структуре, скрывает все индексаторы базового класса, имеющие одинаковую сигнатуру.  
  
 Совместное использование модификаторов `new` и [override](../../../csharp/language-reference/keywords/override.md) в одном члене является недопустимым, поскольку два модификатора имеют взаимоисключающие значения.  Модификатор `new` создает новый член с таким же именем и приводит к скрытию исходного члена.  Модификатор `override` расширяет реализацию для наследуемого члена.  
  
 При использовании модификатора `new` в объявлении, которое не скрывает наследуемый член, возникает предупреждение.  
  
## Пример  
 В этом примере базовый класс `BaseC` и производный класс `DerivedC` используют одно и то же имя поля `x`, которое скрывает значение унаследованного поля.  В примере показано использование модификатора `new`.  Здесь также показано обращение к скрытым членам базового класса с помощью их полных имен.  
  
 [!CODE [csrefKeywordsOperator#9](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsOperator#9)]  
  
## Пример  
 В этом примере вложенный класс скрывает класс, имеющий такое же имя в базовом классе.  Здесь показано использование модификатора `new` для исключения предупреждений, а также обращение к членам скрытого класса с помощью их полных имен.  
  
 [!CODE [csrefKeywordsOperator#10](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsOperator#10)]  
  
 В случае удаления модификатора `new` программа продолжит компиляцию и выполнение, однако появится следующее предупреждение.  
  
```  
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.  
```  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [Управление версиями с помощью ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)   
 [Использование ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)