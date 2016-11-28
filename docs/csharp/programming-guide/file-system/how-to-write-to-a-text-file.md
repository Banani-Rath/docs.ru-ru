---
title: "Практическое руководство. Запись в текстовый файл (Руководство по программированию на C#) | Microsoft Docs"
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
  - "TextWriter.WriteLine"
  - "StreamWriter.Close"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "файлы [C#], текстовые файлы"
  - "текст, запись в файлы [C#]"
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Запись в текстовый файл (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этих примерах показаны различные способы записи текста в файл.  В первых двух примерах используются удобные статические методы класса <xref:System.IO.File?displayProperty=fullName> для записи каждого элемента любой IEnumerable\<строка\> и строки в текстовый файл.  В примере 3 показано, как добавить текст в файл, если необходимо обрабатывать отдельно каждую строку по мере ее записи в файл.  В примерах 1–3 перезаписывается все существующее содержимое файла, а в примере 4 показано, как добавить текст в существующий файл.  
  
 Во всех этих примерах осуществляется запись строковых литералов в файлы, но, вероятнее всего, вы будете использовать метод <xref:System.String.Format%2A>, который содержит множество параметров для записи различных типов значений, с выравниванием по левому или правому краю поля, с заполнением или без и т. д.  Вы также можете использовать функцию [интерполяции строк](../../../csharp/language-reference/keywords/interpolated-strings.md) C\#.  
  
## Пример  
 [!CODE [csFilesandFolders#3](../CodeSnippet/VS_Snippets_VBCSharp/csFilesAndFolders#3)]  
  
 Во всех этих примерах осуществляется запись строковых литералов в файлы, но, вероятнее всего, вы будете использовать метод <xref:System.String.Format%2A>, который содержит множество параметров для записи различных типов значений, с выравниванием по левому или правому краю поля, с заполнением или без и т. д.  Вы также можете использовать функцию [интерполяции строк](../../../csharp/language-reference/keywords/interpolated-strings.md) C\#.  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Файл существует и является файлом только для чтения.  
  
-   Имя пути имеет слишком большую длину.  
  
-   Диск может быть переполнен.  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)   
 [Пример. Сохранение коллекции настраиваемых объектов в локальном хранилище](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)