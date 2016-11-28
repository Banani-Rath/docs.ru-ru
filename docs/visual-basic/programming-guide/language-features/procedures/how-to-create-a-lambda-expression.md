---
title: "Практическое руководство. Создание лямбда-выражения (Visual Basic) | Microsoft Docs"
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
  - "выражения [Visual Basic], лямбда-оператор"
  - "лямбда-выражения [Visual Basic]"
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Создание лямбда-выражения (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*Лямбда\-выражение* — это функция или подпрограмма без имени.  Лямбда\-выражение можно использовать везде, где допустим тип делегата.  
  
### Создание одностроковой функции\-лямбда\-выражения  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере.  
  
     `Dim add1 =`   `Function`  
  
2.  В скобках непосредственно после `Function` введите параметры функции.  Обратите внимание, что после `Function` имя не указано.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  Вслед за списком параметров введите одно выражение как тело функции.  Значение, которое выражение вычисляет, — это значение, возвращаемое функцией.  Не используйте предложение `As` для указания возвращаемого типа.  
  
     [!CODE [VbVbalrLambdas#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#1)]  
  
     Лямбда\-выражение вызывается путем передачи ему целочисленного аргумента.  
  
     [!CODE [VbVbalrLambdas#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#2)]  
  
4.  Кроме того, тот же результат достигается в следующем примере:  
  
     [!CODE [VbVbalrLambdas#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#3)]  
  
### Создание одностроковой подпрограммы\-лямбда\-выражения  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере.  
  
     `Dim add1 =`   `Sub`  
  
2.  В скобках непосредственно после слова `Sub` введите параметры подпрограммы.  Обратите внимание, что после `Sub` имя не указано.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  Вслед за списком параметров введите один оператор как тело подпрограммы.  
  
     [!CODE [VbVbalrLambdas#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#17)]  
  
     Лямбда\-выражение вызывается путем передачи строкового аргумента.  
  
     [!CODE [VbVbalrLambdas#18](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#18)]  
  
### Создание многостроковой функции\-лямбда\-выражения  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере.  
  
     `Dim add1 =`   `Function`  
  
2.  В скобках непосредственно после `Function` введите параметры функции.  Обратите внимание, что после `Function` имя не указано.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Нажмите клавишу ВВОД.  Оператор `End Function` добавляется автоматически.  
  
4.  В тело функции добавьте следующий код, чтобы создать выражение и вернуть значение.  Не используйте предложение `As` для указания возвращаемого типа.  
  
     [!CODE [VbVbalrLambdas#19](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#19)]  
  
     Лямбда\-выражение вызывается путем передачи ему целочисленного аргумента.  
  
     [!CODE [VbVbalrLambdas#20](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#20)]  
  
### Создание многостроковой подпрограммы\-лямбда\-выражения  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере.  
  
     `Dim add1 =`   `Sub`  
  
2.  В скобках непосредственно после слова `Sub` введите параметры подпрограммы.  Обратите внимание, что после `Sub` имя не указано.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Нажмите клавишу ВВОД.  Оператор `End Sub` добавляется автоматически.  
  
4.  В тело функции добавьте следующий код для выполнения при вызове подпрограммы.  
  
     [!CODE [VbVbalrLambdas#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#21)]  
  
     Лямбда\-выражение вызывается путем передачи строкового аргумента.  
  
     [!CODE [VbVbalrLambdas#22](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#22)]  
  
## Пример  
 Обычно лямбда\-выражения используются для определения функции, которая может быть передана в качестве аргумента для параметра типа `Delegate`.  В следующем примере метод <xref:System.Diagnostics.Process.GetProcesses%2A> возвращает массив процессов, выполняющихся на локальном компьютере.  Метод <xref:System.Linq.Enumerable.Where%2A> класса <xref:System.Linq.Enumerable> требует делегат типа `Boolean` в качестве аргумента.  Для этой цели в примере используется лямбда\-выражение.  Оно возвращает `True` для каждого процесса, у которого есть только один поток. Такие процессы выбираются в `filteredList`.  
  
 [!CODE [VbVbalrLambdas#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#10)]  
  
 Приведенный пример эквивалентен следующему коду, написанному в синтаксисе [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]:  
  
 [!CODE [VbVbalrLambdas#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#11)]  
  
## См. также  
 <xref:System.Linq.Enumerable>   
 [Лямбда\-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Практическое руководство. Передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)