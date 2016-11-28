---
title: "Практическое руководство. Отображение аргументов командной строки (Руководство по программированию на C#) | Microsoft Docs"
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
  - "аргументы командной строки [C#], отображение"
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Отображение аргументов командной строки (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Для доступа к аргументам, предоставленным для исполняемого файла в командной строке, можно использовать необязательный параметр для `Main`.  Аргументы представлены в форме массива или строк.  Каждый элемент массива содержит один аргумент.  Пробел между элементами удален.  Например, рассмотрим следующие вызовы вымышленного исполняемого файла из командной строки.  
  
|Данные, вводимые в командную строку|Массив строк, переданный в Main|  
|-----------------------------------------|-------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe один два**|"один"<br /><br /> "два"|  
|**executable.exe "один два" три**|"один два"<br /><br /> "три"|  
  
> [!NOTE]
>  При выполнении приложения в Visual Studio можно указать аргументы командной строки в [Страница "Отладка" в конструкторе проектов](/visual-studio/ide/reference/debug-page-project-designer).  
  
## Пример  
 В этом примере показаны аргументы командной строки, переданные в приложение командной строки.  Далее представлен результат для первой записи в расположенной выше таблице.  
  
 [!CODE [csProgGuideMain#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideMain#9)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Main\(\) и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Значения, возвращаемые методом Main\(\)](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)