---
title: "Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми в Visual Basic | Microsoft Docs"
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
  - "файлы, синтаксический разбор"
  - "чтение текстовых файлов, разделенных запятыми"
  - "текстовые файлы, чтение"
  - "текстовые файлы, задачи"
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объект `TextFieldParser` позволяет легко и эффективно анализировать структурированные текстовые файлы, например файлы журналов.  Свойство `TextFieldType` определяет, является ли файл файлом с разделителями или с полями фиксированной ширины текста.  
  
### Анализ текстового файла, разделенного запятыми  
  
1.  Создайте новый объект `TextFieldParser`.  Следующий код создает объект `TextFieldParser` с именем `MyReader` и открывает файл `test.txt`.  
  
     [!CODE [VbFileIORead#15](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#15)]  
  
2.  Определите тип и разделитель `TextField`.  В следующем коде определяются свойство `TextFieldType` как `Delimited`, а в качестве разделителя задается символ ",".  
  
     [!CODE [VbFileIORead#16](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#16)]  
  
3.  Переберите в цикле поля файла.  Если какие\-либо строки повреждены, выведите сообщение об ошибке и продолжите анализ.  Следующий код просматривает файл в цикле, отображая каждое поле по очереди и сообщая о тех полях, которые сформатированы неправильно.  
  
     [!CODE [VbFileIORead#17](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#17)]  
  
4.  Закройте блоки `While` и `Using` операторами `End While` и `End Using`.  
  
     [!CODE [VbFileIORead#18](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#18)]  
  
## Пример  
 В этом примере производится чтение данных из файла `test.txt`.  
  
 [!CODE [VbFileIORead#19](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#19)]  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Строка не может быть проанализирована с использованием указанного формата \(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  Сообщение исключения задает строку, вызвавшую исключение, а свойство <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> присвоено тексту, который содержится в строке.  
  
-   Заданный файл не существует \(<xref:System.IO.FileNotFoundException>\).  
  
-   Ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений для доступа к файлу.  \(<xref:System.Security.SecurityException>\).  
  
-   Путь слишком длинный \(<xref:System.IO.PathTooLongException>\).  
  
-   Пользователь не имеет необходимых разрешений для доступа к файлу \(<xref:System.UnauthorizedAccessException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 [Практическое руководство. Чтение из текстовых файлов с фиксированной шириной полей](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [Практическое руководство. Чтение текстовых файлов различных форматов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Анализ текстовых файлов с помощью объекта TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Пошаговое руководство. Операции с файлами и каталогами в Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Разрешение вопросов, связанных с исключениями: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)