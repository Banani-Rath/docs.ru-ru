---
title: "dynamic (Справочник по C#) | Microsoft Docs"
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
  - "dynamic_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "dynamic [C#]"
  - "ключевое слово dynamic [C#]"
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# dynamic (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Тип `dynamic` позволяет пропускать проверки типов во время компиляции операции, в которых он применяется .  Вместо этого эти операции разрешаются во время выполнения.  Тип `dynamic` упрощает доступ к API модели COM, например API автоматизации Office, к динамическим API, например библиотекам IronPython, и модели DOM HTML.  
  
 В большинстве случаев тип `dynamic` ведет себя так же, как `object`.  Однако операции, которые содержат выражения типа `dynamic`, не разрешаются, или выполняется проверка типа компилятором.  Компилятор пакует сведения об операции, затем эти сведения используются для оценки операции во время выполнения.  Как часть процесса, переменные типа `dynamic` компилируются в переменные типа `object`.  Поэтому тип `dynamic` существует только во время компиляции, но не во время выполнения.  
  
 В следующем примере переменная типа `dynamic` противопоставляется переменной типа `object`.  Чтобы проверить тип каждой переменной во время компиляции, наведите указатель мыши на `dyn` или `obj` в операторах `WriteLine`.  IntelliSense отображает **dynamic** для `dyn` и **object** для `obj`.  
  
 [!CODE [csrefKeywordsTypes#21](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsTypes#21)]  
  
 Инструкции `WriteLine` отображают типы времени выполнения `dyn` и `obj`.  На этом этапе оба имеют одинаковый тип "целое число".  Следующие выходные данные являются результатом:  
  
 `System.Int32`  
  
 `System.Int32`  
  
 Чтобы понять различие между `dyn` и `obj` во время компиляции, добавьте следующие две строки между объявлениями и операторами `WriteLine` в предыдущем примере.  
  
```c#  
dyn = dyn + 3;  
obj = obj + 3;  
  
```  
  
 При попытке добавления целого числа или объекта в выражение `obj + 3` выводится ошибка компиляции.  Однако нет сообщений об ошибках для `dyn + 3` .  Выражение, содержащее `dyn`, не проверяется во время компиляции, поскольку тип `dyn` задан как `dynamic`.  
  
## Контекст  
 Ключевое слово `dynamic` может отображаться непосредственно или как компонент сконструированного типа в следующих ситуациях:  
  
-   В объявлениях в качестве типа свойства, поля, индексатор, параметра, возвращаемого значения, локальной переменной или ограничения типа.  Следующее определение класса использует `dynamic` в нескольких различных объявлениях.  
  
     [!CODE [csrefKeywordsTypes#22](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsTypes#22)]  
  
-   В преобразованиях явного типа в качестве типа целевого объекта преобразования.  
  
     [!CODE [csrefKeywordsTypes#23](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsTypes#23)]  
  
-   В любом контексте, где типы служат в качестве значений, например как типы с правой стороны оператора `is` или `as`, или как аргумент в `typeof` в качестве части сконструированного типа.  Например, `dynamic` можно использовать в следующих выражениях.  
  
     [!CODE [csrefKeywordsTypes#24](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsTypes#24)]  
  
## Пример  
 В следующем примере `dynamic` используется в нескольких объявлениях.  Метод `Main` также противопоставляет проверку типов во время выполнения проверке типов во время компиляции.  
  
 [!CODE [csrefKeywordsTypes#25](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsTypes#25)]  
  
 Дополнительные сведения и примеры см. в разделе [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).  
  
## См. также  
 <xref:System.Dynamic.ExpandoObject?displayProperty=fullName>   
 <xref:System.Dynamic.DynamicObject?displayProperty=fullName>   
 [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [объект](../../../csharp/language-reference/keywords/object.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [as](../../../csharp/language-reference/keywords/as.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 [Практическое руководство. Безопасное приведение с помощью операторов as и is](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)   
 [Пошаговое руководство. Создание и использование динамических объектов](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)