---
title: "Main() и аргументы командной строки (Руководство по программированию на C#) | Microsoft Docs"
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
  - "CS5001"
  - "main_CSharpKeyword"
  - "Main"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "аргументы [C#], командная строка"
  - "C# - язык, аргументы командной строки"
  - "командная строка [C#], аргументы"
  - "аргументы командной строки [C#], Main - метод"
  - "Main - метод [C#]"
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
caps.latest.revision: 30
caps.handback.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Main() и аргументы командной строки (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Метод  `Main` является точкой входа консольного приложения C\# или приложения Windows.  \(Для библиотек и служб не требуется метод `Main` в качестве точки входа\).  При запуске приложения метод `Main` является первым вызываемым методом.  
  
 В программе C\# возможна только одна точка входа.  Если в наличие имеется больше одного класса, который имеет метод `Main`, то необходимо скомпилировать программу с параметром компилятора **\/main**, чтобы указать, какой метод `Main` нужно использовать в качестве точки входа.  Дополнительные сведения см. в разделе [\/main \(Specify Location of Main Method\)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).  
  
 [!CODE [csProgGuideMain#17](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideMain#17)]  
  
## Общие сведения  
  
-   Метод `Main` является точкой входа EXE\-программы, в которой начинается и заканчивается управление программой.  
  
-   Метод `Main` объявлен внутри класса или структуры.  `Main` должно быть [статический](../../../csharp/language-reference/keywords/static.md) и это не должно быть [открытый](../../../csharp/language-reference/keywords/public.md).  \(В предыдущем примере он получает доступ по умолчанию типа [закрытый](../../../csharp/language-reference/keywords/private.md).\) Включающий класс или структура не обязательно должна быть статической.  
  
-   `Main` может иметь возвращаемый тип либо `void`, либо `int`.  
  
-   Метод `Main` может быть объявлен с параметром `string[]`, который содержит аргументы командной строки, или без него.  При использовании [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] для создания приложений Windows Forms, можно добавить параметр вручную или использовать класс <xref:System.Environment> для получения аргументов командной строки.  Параметры считываются в качестве нулевым индексированные аргументы командной строки. В отличие от C C и C\-\+\+, имя программы не рассматривается как первый аргумент командной строки.  
  
## Содержание  
  
-   [Аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)  
  
-   [Практическое руководство. Отображение аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
  
-   [Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
  
-   [Значения, возвращаемые методом Main\(\)](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Структура программы C\#](../../../csharp/programming-guide/inside-a-program/index.md)   
 [\<paveover\>C\# Sample Applications](http://msdn.microsoft.com/ru-ru/9a9d7aaa-51d3-4224-b564-95409b0f3e15)