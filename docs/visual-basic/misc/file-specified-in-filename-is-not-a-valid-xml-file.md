---
title: "Файл, указанный в FileName, не является допустимым XML-файлом | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Файл, указанный в FileName, не является допустимым XML-файлом
Указанное имя файла не представляет допустимый XML\-файл. Чтобы задать допустимую структуру и содержимое XML\-документа, можно использовать схему DTD, Microsoft XML\-Data Reduced \(XDR\) или языка определения схемы XML. Для указания грамматики XML в [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)] предпочтительнее использовать схемы XSD.  
  
> [!NOTE]
>  В некоторых более ранних версиях Visual Studio **конструктор XML** — это конструктор для типизированных наборов данных и схемы XML.**Конструктор XML** по\-прежнему можно использовать для создания и редактирования файлов схемы XML. Однако в [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)] для создания и редактирования типизированных наборов данных используется **конструктор наборов данных**. Для получения дополнительной информации см. [Создание и изменение типизированных наборов данных](/visual-studio/data-tools/creating-and-editing-typed-datasets).  
  
### Исправление ошибки  
  
-   Убедитесь, что вы указали правильное имя файла.  
  
-   Убедитесь, что указанный файл содержит допустимый XML, загрузив XML\-файл, который требуется проверить, в **конструктор XML**. В меню **XML** выберите **Проверить XML**. Ошибки отображаются в **списке задач**.  
  
-   Если XML\-файл имеет связанную схему XML, удостоверьтесь, что элементы существуют в определенной структуре и что содержимое отдельных элементов соответствует объявленным типам данных, указанным в схеме.  
  
## См. также  
 <xref:System.Xml>   
 [Практическое руководство. Анализ путей к файлам](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)