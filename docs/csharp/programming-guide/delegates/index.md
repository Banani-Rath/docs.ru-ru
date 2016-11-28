---
title: "Делегаты (Руководство по программированию на C#) | Microsoft Docs"
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
  - "C# - язык, делегаты"
  - "делегаты [C#]"
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
caps.latest.revision: 30
caps.handback.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Делегаты (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[Делегат](../../../csharp/language-reference/keywords/delegate.md) — это тип, представляющий ссылки на методы с конкретным списком параметров и возвращаемым типом.  При создании экземпляра делегата этот экземпляр можно связать с любым методом с совместимой сигнатурой и возвращаемым типом.  Метод можно вызвать \(активировать\) с помощью экземпляра делегата.  
  
 Делегаты используются для передачи методов в качестве аргументов к другим методам.  Обработчики событий — это ничто иное, как методы, вызываемые с помощью делегатов.  При создании пользовательского метода класс \(например, элемент управления Windows\) может вызывать этот метод при появлении определенного события.  В следующем примере показано объявление делегата:  
  
 [!CODE [csProgGuideDelegates#20](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#20)]  
  
 Делегату можно назначить любой метод из любого доступного класса или структуры, соответствующей типу делегата.  Этот метод должен быть статическим методом или методом экземпляра.  Это позволяет программно изменять вызовы метода, а также включать новый код в существующие классы.  
  
> [!NOTE]
>  В контексте перегрузки метода его сигнатура не содержит возвращаемое значение.  Однако в контексте делегатов сигнатура метода содержит возвращаемое значение.  Другими словами, метод должен иметь тот же возвращаемый тип, что и делегат.  
  
 Благодаря возможности ссылаться на метод как на параметр делегаты идеально подходят для определения методов обратного вызова.  Например, ссылка на метод, сравнивающий два объекта, может быть передана в качестве аргумента алгоритму сортировки.  Поскольку код сравнения находится в отдельной процедуре, алгоритм сортировки может быть написан более общим способом.  
  
## Общие сведения о делегатах  
 Делегаты имеют следующие свойства.  
  
-   Делегаты похожи на указатели функций в C\+\+, но являются типобезопасными.  
  
-   Делегаты допускают передачу методов в качестве параметров.  
  
-   Делегаты можно использовать для определения методов обратного вызова.  
  
-   Делегаты можно связывать друг с другом; например, при появлении одного события можно вызывать несколько методов.  
  
-   Точное соответствие методов типу делегата не требуется.  Дополнительные сведения см. в разделе [Использование вариативности в делегатах](../Topic/Using%20Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md).  
  
-   В C\# версии 2.0 введена концепция [анонимных методов](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), которые позволяют передавать блоки кода в виде параметров вместо использования отдельно определенного метода.  В C\# 3.0 для краткой записи встроенных блоков кода введены лямбда\-выражения.  В результате компиляции как анонимных методов, так и лямбда\-выражений \(в определенном контексте\) получаются типы делегатов.  В настоящее время эти возможности называются анонимными функциями.  Дополнительные сведения о лямбда\-выражениях см. в разделе [Анонимные функции](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## Содержание  
  
-   [Использование делегатов](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [When to Use Delegates Instead of Interfaces \(C\# Programming Guide\)](http://msdn.microsoft.com/ru-ru/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [Делегаты с именованными методами и делегаты с анонимными методами](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [Использование вариативности в делегатах](../Topic/Using%20Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md)  
  
-   [Практическое руководство. Объединение делегатов \(многоадресные делегаты\)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [Практическое руководство. Объявление, создание и использование делегата](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Главы в популярных книгах  
 [Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) в [C\# 3.0 Cookbook, Third Edition: More than 250 solutions for C\# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)  
  
 [Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) в [Learning C\# 3.0: Master the fundamentals of C\# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)  
  
## См. также  
 <xref:System.Delegate>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [События](../../../csharp/programming-guide/events/index.md)