---
title: "Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "определение имен свойств [Visual Basic]"
  - "анонимные типы [Visual Basic], определение имен и типов свойств"
  - "определение типов свойств [Visual Basic]"
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Анонимные типы не предоставляют механизм для прямого указания типов данных для свойств. Типы всех свойств определяются посредством вывода. В следующем примере типы `Name` и `Price` выводятся напрямую из значений, которые используются для их инициализации.  
  
 [!CODE [VbVbalrAnonymousTypes#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#1)]  
  
 Анонимные типы также могут выводить имена и типы свойств из других источников. В последующих разделах представлен список ситуаций, где вывод возможен, и примеры обратных ситуаций.  
  
## Успешный вывод  
  
#### Анонимные типы могут выводить имена и типы свойств из следующих источников.  
  
-   Из имен переменных. Анонимный тип `anonProduct` будет иметь два свойства: `productName` и `productPrice`. Их типами данных будут типы исходных переменных, `String` и `Double` соответственно.  
  
     [!CODE [VbVbalrAnonymousTypes#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#11)]  
  
-   Из имен свойств или полей других объектов. Например, рассмотрим объект `car` типа `CarClass`, включающий свойства `Name` и `ID`. Чтобы создать новый экземпляр анонимного типа `car1` со свойствами `Name` и `ID`, которые инициализируются значениями из объекта `car`, можно написать следующее.  
  
     [!CODE [VbVbalrAnonymousTypes#34](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#34)]  
  
     Предыдущее объявление эквивалентно большей строке кода, определяющей анонимный тип `car2`.  
  
     [!CODE [VbVbalrAnonymousTypes#35](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#35)]  
  
-   Из имен элементов XML  
  
     [!CODE [VbVbalrAnonymousTypes#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#12)]  
  
     Результирующий тип для `anon` будет иметь одно свойство `Book` c типом <xref:System.Collections.IEnumerable> \(XElement\).  
  
-   Из функции, которая не имеет параметров, например `SomeFunction` в следующем примере.  
  
     `Dim sc As New SomeClass`  
  
     `Dim anon1 = New With {Key sc.SomeFunction()}`  
  
     Переменная `anon2` в следующем коде является анонимным типом, который имеет одно свойство: знак с именем `First`. Этот код будет отображать букву E — букву, которая возвращена функцией <xref:System.Linq.Enumerable.First%2A>.  
  
     [!CODE [VbVbalrAnonymousTypes#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#13)]  
  
## Неудачный вывод  
  
#### Вывод имени завершится сбоем во многих случаях, в том числе в следующих.  
  
-   Вывод является производным от вызова метода, конструктора или параметризованного свойства, для которого требуются аргументы. Предыдущее объявление `anon1` завершается сбоем, если `someFunction` имеет один или несколько аргументов.  
  
     `' Not valid.`  
  
     `' Dim anon3 = New With {Key sc.someFunction(someArg)}`  
  
     Проблема решается путем назначения новому имени свойства.  
  
     `' Valid.`  
  
     `Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}`  
  
-   Вывод является производным от сложного выражения.  
  
    ```  
    Dim aString As String = "Act "  
    ' Not valid.  
    ' Dim label = New With {Key aString & "IV"}  
    ```  
  
     Ошибку можно устранить, назначив результат выражения для имени свойства.  
  
     [!CODE [VbVbalrAnonymousTypes#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#14)]  
  
-   Вывод нескольких свойств создает два или более свойств с одинаковым именем. Возвращаясь к объявлениям в предыдущих примерах, невозможно указывать `product.Name` и `car1.Name` в качестве свойств для одного анонимного типа. Это связано с тем, что выводимый идентификатор для каждого из них будет `Name`.  
  
     `' Not valid.`  
  
     `' Dim anon5 = New With {Key product.Name, Key car1.Name}`  
  
     Проблему можно решить, назначив значения уникальным именам свойств.  
  
     [!CODE [VbVbalrAnonymousTypes#36](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#36)]  
  
     Обратите внимание, что изменение регистра \(изменение прописных букв на строчные и наоборот\) не делает имя уникальным.  
  
     `Dim price = 0`  
  
     `' Not valid, because Price and price are the same name.`  
  
     `' Dim anon7 = New With {Key product.Price, Key price}`  
  
-   Исходные тип и значение одного свойства зависят от другого свойства, которое еще не установлено. Например, `.IDName = .LastName` не является допустимым в объявлении анонимного типа, если только `.LastName` уже не инициализирован.  
  
     `' Not valid.`  
  
     `' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}`  
  
     В этом примере проблему можно устранить, изменив порядок, в котором объявлены свойства, на обратный.  
  
     [!CODE [VbVbalrAnonymousTypes#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#15)]  
  
-   Имя свойства анонимного типа совпадает с именем элемента <xref:System.Object>. Например, следующее объявление завершится сбоем, так как `Equals` — это метод <xref:System.Object>.  
  
     `' Not valid.`  
  
     `' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _`  
  
     `'                       "greater than", Key .Less = "less than"}`  
  
     Проблему можно устранить, изменив имя свойства:  
  
     [!CODE [VbVbalrAnonymousTypes#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#16)]  
  
## См. также  
 [Инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)