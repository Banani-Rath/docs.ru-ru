---
title: "Практическое руководство. Преобразование массива байтов в строку в Visual Basic | Microsoft Docs"
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
  - "массивы [Visual Basic], преобразование в строки"
  - "массивы байтов, преобразование в строки"
  - "примеры [Visual Basic], строки"
  - "преобразование строк, массивы"
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Преобразование массива байтов в строку в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом разделе показано, как преобразовать байты из массива байтов в строку.  
  
## Пример  
 В этом примере используется метод <xref:System.Text.Encoding.GetString%2A> из класса кодирования <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName> для преобразования всех байтов из массива байтов в строку.  
  
 [!CODE [VbVbalrStrings#72](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#72)]  
  
 Можно выбрать из нескольких параметров кодирования для преобразования в массива байтов в строку:  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName>: возвращает кодировку для ASCII \(7 разрядов\).  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=fullName>: возвращает кодировку для формата UTF\-16 с обратным порядком байтов.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=fullName>: возвращает кодировку для текущей системной кодовой страницы ANSI.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName>: возвращает кодировку для формата UTF\-16 с прямым порядком байтов.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=fullName>: возвращает кодировку для формата UTF\-32 с прямым порядком байтов.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=fullName>: возвращает кодировку для формата UTF\-7.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=fullName>: возвращает кодировку для формата UTF\-8.  
  
## См. также  
 <xref:System.Text.Encoding?displayProperty=fullName>   
 <xref:System.Text.Encoding.GetString%2A>   
 [Практическое руководство. Преобразование строки в массив байтов в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)