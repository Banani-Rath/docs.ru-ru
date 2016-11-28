---
title: "Константы (Руководство по программированию на C#) | Microsoft Docs"
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
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Константы (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Константы представляют собой неизменные значения, известные во время компиляции и неизменяемые на протяжении времени существования программы.  Константы объявляются с модификатором [const](../../../csharp/language-reference/keywords/const.md).  Только встроенные типы C\# \(за исключением <xref:System.Object?displayProperty=fullName>\) могут быть объявлены как `const`.  Список встроенных типов см. в разделе [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md).  Определяемые пользователем типы, включая классы, структуры и массивы, не могут быть `const`.  Для создания класса, структуры или массива, которые инициализируются один раз во время выполнения \(например, в конструкторе\) и после этого не могут быть изменены, используется модификатор [readonly](../../../csharp/language-reference/keywords/readonly.md).  
  
 Язык C\# не поддерживает методы, свойства и события с ключевым словом `const`.  
  
 Тип перечисления позволяет определять именованные константы для целочисленных встроенных типов \(например, `int`, `uint`, `long` и т. д.\).  Дополнительные сведения см. в разделе [перечисление](../../../csharp/language-reference/keywords/enum.md).  
  
 Константы должны инициализировать сразу после объявления.  Примеры.  
  
 [!CODE [csProgGuideObjects#64](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#64)]  
  
 В этом примере константа `months` всегда имеет значение 12, и ее значение не может быть изменено даже самим классом.  Когда компилятор встречает идентификатор константы в исходном коде C\# \(например, `months`\), он подставляет литеральное значение непосредственно в его создающий код IL.  Поскольку адрес переменной, связанный с константой во время выполнения, отсутствует, поля `const` не могут быть переданы по ссылке и отображены как значение l\-value в выражении.  
  
> [!NOTE]
>  При ссылке на значения констант, определенных в другом коде, например DLL, следует соблюдать осторожность.  Если новое значение константы определяется в новой версии DLL, программа по\-прежнему будет хранить старое литеральное значение вплоть до перекомпиляции в новую версию.  
  
 Несколько констант одного типа можно объявить одновременно, например:  
  
 [!CODE [csProgGuideObjects#65](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#65)]  
  
 Используемое для инициализации константы выражение может ссылаться на другую константу, если при этом не создается циклическая ссылка.  Примеры.  
  
 [!CODE [csProgGuideObjects#66](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#66)]  
  
 Константы могут быть отмечены модификаторами [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) или `protected` `internal`.  Эти модификаторы доступа определяют порядок доступа к константе для пользователей класса.  Дополнительные сведения см. в разделе [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Доступ к константам осуществляется так, как если бы они были [статическими](../../../csharp/language-reference/keywords/static.md) полями, поскольку значение константы одинаково для всех экземпляров типа.  Для их объявления не нужно использовать ключевое слово `static`.  В выражениях, которые не входят в класс, в котором определена константа, для доступа к ней необходимо использовать имя класса, точку и имя этой константы.  Примеры.  
  
 [!CODE [csProgGuideObjects#67](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#67)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Типы](../../../csharp/programming-guide/types/index.md)   
 [readonly](../../../csharp/language-reference/keywords/readonly.md)   
 [Immutability in C\# Part One: Kinds of Immutability](http://go.microsoft.com/fwlink/?LinkId=112379)