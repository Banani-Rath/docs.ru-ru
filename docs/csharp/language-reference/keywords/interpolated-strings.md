---
title: "Интерполированные строки (Справочник по C# и Visual Basic) | Microsoft Docs"
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
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Интерполированные строки (Справочник по C# и Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Используется для создания строк.  Интерполированное строковое выражение выглядит как шаблонная строка, которая содержит выражения.  Интерполированное строковое выражение создает строку, заменяя содержащиеся выражения представлениями ToString результатов выражений.  Интерполированную строку проще понять с точки зрения аргументов, чем [Составное форматирование](../Topic/Composite%20Formatting.md).  Ниже приведен пример интерполированной строки:  
  
```c#  
Console.WriteLine($"Name = {name}, hours = {hours:hh}")  
```  
  
 Структура интерполированной строки выглядит следующим образом:  
  
```  
$ " <text> { <interpolation-expression> <optional-comma-field-width> <optional-colon-format> } <text> ... } "  
```  
  
 Интерполированную строку можно использовать везде, где допустимо применять строковый литерал.  В ходе работы программа будет выполнять код с интерполированным строковым литералом, а код будет вычислять новый строковый литерал путем оценки выражений интерполяции.  Это вычисление происходит каждый раз, когда выполняется код с интерполированной строкой.  
  
 Чтобы включить в интерполированную строку фигурные скобки \(«{» или «}»\), используйте две фигурные скобки — «{{» или «}}».  Дополнительные сведения см в разделе «Неявные преобразования».  
  
## Неявные преобразования  
 Предусмотрены неявные преобразования типов из интерполированных строк.  
  
```c#  
var s = $"hello, {name}" System.IFormattable s = $"Hello, {name}" System.FormattableString s = $"Hello, {name}"  
  
```  
  
 В первом примере получается значение `string`, где были вычислены все строковые значения интерполяции.  Это окончательный результат, который имеет строковый тип.  Все вхождения двойных фигурных скобок \(«{{» и «}}»\) преобразуются в одиночную фигурную скобку.  
  
 Во втором примере получается переменная <xref:System.IFormattable>, которая позволяет преобразовать строку с инвариантным контекстом.  Это полезно для получения числовых форматов и форматов данных, корректных в разных языках.  Все вхождения двойных фигурных скобок \(«{{» и «}}»\) остаются двойными фигурными скобками, пока вы не примените для форматирования строки ToString.  Все заключенные в скобки выражения интерполяции преобразуются в {0}, \\{1\\} и т. д.  
  
```c#  
s.ToString(null, System.Globalization.CultureInfo.InvariantCulture);  
```  
  
 В третьем примере получается <xref:System.FormattableString>, что позволяет проверять объекты, которые возникают в результате вычисления интерполяции.  Проверка объектов и способа их отрисовки в виде строк может, например, обеспечивать защиту от атак путем внедрения кода, если выполнялось построение запроса.<xref:System.FormattableString> позволяет выполнять удобные операции для получения строковых результатов InvariantCulture и CurrentCulture.  Все вхождения двойных фигурных скобок \(«{{» и «}}»\) остаются двойными фигурными скобками, пока не выполнено форматирование.  Все заключенные в скобки выражения интерполяции преобразуются в {0}, \\{1\\} и т. д.  
  
## Примеры  
  
```c#  
$"Name = {name}, hours = {hours:hh}" var s = $"hello, {name}" System.IFormattable s = $"Hello, {name}" System.FormattableString s = $"Hello, {name}" $"{person.Name, 20} is {person.Age:D3} year {(p.Age == 1 ? "" : "s")} old."  
  
```  
  
 Внутри заключенных в кавычки выражений интерполяции кавычки не нужно заключать еще в одни кавычки, так как интерполированные строковые выражения начинаются с символа $ и компилятор проверяет заключенное в кавычки выражение интерполяции как сбалансированный текст до тех пор, пока не найдет запятую, двоеточие или закрывающую фигурную скобку.  По этим же причинам в последнем примере используются круглые скобки, позволяющие условному выражению \(`p.Age == 1 ? "" : "s"`\) находиться внутри выражения интерполяции без двоеточия, которое является началом спецификации формата.  За пределами заключенного в кавычки выражения интерполяции \(но по\-прежнему внутри интерполированного строкового выражения\) кавычки следует преобразовывать в escape\-последовательность обычным способом.  
  
## Синтаксис  
  
```  
expression: interpolated-string-expression interpolated-string-expression: interpolated-string-start interpolations interpolated-string-end interpolations: single-interpolation single-interpolation interpolated-string-mid interpolations single-interpolation: interpolation-start interpolation-start : regular-string-literal interpolation-start: expression expression , expression  
  
```  
  
## Спецификации языков  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
 Более подробную информацию см. в разделе [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## См. также  
 <xref:System.IFormattable?displayProperty=fullName>   
 <xref:System.FormattableString?displayProperty=fullName>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)   
 [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)