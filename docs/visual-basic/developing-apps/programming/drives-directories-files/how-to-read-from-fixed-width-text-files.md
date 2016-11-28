---
title: "Практическое руководство. Чтение из текстовых файлов с фиксированной шириной полей в Visual Basic | Microsoft Docs"
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
  - "текстовый файл с фиксированной шириной"
  - "чтение текстовых файлов, фиксированная ширина"
  - "текстовые файлы, чтение"
  - "текстовые файлы, задачи"
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Чтение из текстовых файлов с фиксированной шириной полей в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объект `TextFieldParser` позволяет легко и эффективно анализировать структурированные текстовые файлы, например файлы журналов.  
  
 Свойство `TextFieldType` определяет, является ли проанализированный файл файлом с разделителями или файлом с полями фиксированной ширины текста.  В текстовом файле с полями фиксированного размера поле в конце может иметь переменную ширину.  Чтобы указать, что поле в конце имеет переменную длину, определите для его ширины значение меньше или равное нулю.  
  
### Анализ текстового файла с полями фиксированной ширины  
  
1.  Создайте новый объект `TextFieldParser`.  Следующий код создает объект `TextFieldParser` с именем `Reader` и открывает файл `test.log`.  
  
     [!CODE [VbFileIORead#9](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#9)]  
  
2.  Определите свойство `TextFieldType` как `FixedWidth`, задав ширину и формат.  Следующий код определяет столбцы текста; первый имеет ширину 5 символов, второй 10, третий 11, а четвертый столбец имеет переменную ширину.  
  
     [!CODE [VbFileIORead#10](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#10)]  
  
3.  Переберите в цикле поля файла.  Если какие\-либо строки повреждены, выведите сообщение об ошибке и продолжите анализ.  
  
     [!CODE [VbFileIORead#11](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#11)]  
  
4.  Закройте блоки `While` и `Using` операторами `End While` и `End Using`.  
  
     [!CODE [VbFileIORead#12](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#12)]  
  
## Пример  
 В этом примере производится чтение данных из файла `test.log`.  
  
 [!CODE [VbFileIORead#13](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIORead#13)]  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Строка не может быть проанализирована с использованием указанного формата \(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  Сообщение исключения задает строку, вызвавшую исключение, а свойство <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> присвоено тексту, который содержится в строке.  
  
-   Заданный файл не существует \(<xref:System.IO.FileNotFoundException>\).  
  
-   Ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений для доступа к файлу.  \(<xref:System.Security.SecurityException>\).  
  
-   Путь слишком длинный \(<xref:System.IO.PathTooLongException>\).  
  
-   Пользователь не имеет необходимых разрешений для доступа к файлу \(<xref:System.UnauthorizedAccessException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 [Практическое руководство. Чтение из текстовых файлов с разделителями\-запятыми](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [Практическое руководство. Чтение текстовых файлов различных форматов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Анализ текстовых файлов с помощью объекта TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Пошаговое руководство. Операции с файлами и каталогами в Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Разрешение вопросов, связанных с исключениями: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)