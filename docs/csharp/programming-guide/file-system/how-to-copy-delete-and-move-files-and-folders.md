---
title: "Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#) | Microsoft Docs"
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
  - "ввод-вывод [C#]"
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В следующих примерах показано, как синхронно копировать, перемещать и удалять файлы и папки с использованием классов <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName> и <xref:System.IO.DirectoryInfo?displayProperty=fullName> из пространства имен <xref:System.IO?displayProperty=fullName>.  В этих примерах не используется индикатор хода выполнения или какой\-либо иной пользовательский интерфейс.  Если нужно использовать стандартное диалоговое окна хода выполнения, см. раздел [Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Используйте <xref:System.IO.FileSystemWatcher?displayProperty=fullName> для предоставления событий, которые позволяют вычислять ход выполнения при работе с несколькими файлами.  Другим подходом является использование вызова неуправляемого кода для вызова в Windows Shell методов, относящихся к обработке файлов.  Сведения о способах асинхронного выполнения таких операций над файлами см. раздел [Асинхронный файловый ввод\-вывод](../Topic/Asynchronous%20File%20I-O.md).  
  
## Пример  
 В следующем примере показано, как копировать файлы и каталоги.  
  
 [!CODE [csFilesandFolders#7](../CodeSnippet/VS_Snippets_VBCSharp/csFilesAndFolders#7)]  
  
## Пример  
 В следующем примере показано, как перемещать файлы и каталоги.  
  
 [!CODE [csFilesandFolders#8](../CodeSnippet/VS_Snippets_VBCSharp/csFilesAndFolders#8)]  
  
## Пример  
 В следующем примере показано, как удалять файлы и каталоги.  
  
 [!CODE [csFilesandFolders#9](../CodeSnippet/VS_Snippets_VBCSharp/csFilesAndFolders#9)]  
  
## См. также  
 <xref:System.IO?displayProperty=fullName>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)   
 [Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)   
 [Файловый и потоковый ввод\-вывод](../Topic/File%20and%20Stream%20I-O.md)   
 [Распространенные задачи ввода\-вывода](../Topic/Common%20I-O%20Tasks.md)