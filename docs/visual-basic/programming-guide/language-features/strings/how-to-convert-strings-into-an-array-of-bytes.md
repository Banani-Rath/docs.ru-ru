---
title: "Практическое руководство. Преобразование строки в массив байтов в Visual Basic | Microsoft Docs"
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
  - "массивы [Visual Basic], массивы байтов"
  - "массивы [Visual Basic], преобразование строк в"
  - "массивы байтов"
  - "примеры [Visual Basic], преобразование строк"
  - "преобразование строк, массивы"
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Преобразование строки в массив байтов в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом разделе показано, как преобразовать строку в массив байтов.  
  
## Пример  
 В этом примере метод <xref:System.Text.Encoding.GetBytes%2A> из класса кодировки <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName> используется для преобразования строки в массив байтов.  
  
 [!CODE [VbVbalrStrings#74](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#74)]  
  
 Для преобразования строки в массив байтов можно выбрать один из нескольких параметров кодировки:  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName>: возвращает кодировку для ASCII \(7 разрядов\).  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=fullName>: возвращает кодировку для формата UTF\-16 с обратным порядком байтов.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=fullName>: возвращает кодировку для текущей системной кодовой страницы ANSI.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName>: возвращает кодировку для формата UTF\-16 с прямым порядком байтов.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=fullName>: возвращает кодировку для формата UTF\-32 с прямым порядком байтов.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=fullName>: возвращает кодировку для формата UTF\-7.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=fullName>: возвращает кодировку для формата UTF\-8.  
  
## См. также  
 <xref:System.Text.Encoding?displayProperty=fullName>   
 <xref:System.Text.Encoding.GetBytes%2A>   
 [Практическое руководство. Преобразование массива байтов в строку в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)