---
title: "Практическое руководство. Анализ путей к файлам в Visual Basic | Microsoft Docs"
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
  - "имена файлов, анализ [Visual Basic]"
  - "анализ, пути к файлам [Visual Basic]"
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Анализ путей к файлам в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объект <xref:Microsoft.VisualBasic.FileIO.FileSystem> предоставляет ряд полезных методов при анализе путей к файлам.  
  
-   Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> получает два пути и возвращает комбинированный путь в правильном формате.  
  
-   Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> возвращает абсолютный путь к родительскому элементу указанного пути.  
  
-   Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> возвращает объект <xref:System.IO.FileInfo>, к которому можно выполнить запрос, чтобы определить свойства файла, например имя и путь.  
  
 По расширению файла не всегда можно с уверенностью судить о его содержимом. Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.  
  
### Определение имени и пути для файла  
  
-   Используйте свойства <xref:System.IO.FileInfo.DirectoryName%2A> и <xref:System.IO.FileInfo.Name%2A> объекта <xref:System.IO.FileInfo>, чтобы определить для файла имя и путь. В этом примере определяются и отображаются имя и путь.  
  
     [!CODE [VbVbcnMyFileSystem#54](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#54)]  
  
### Объединение имени и каталога файла для создания полного пути  
  
-   Используйте метод `CombinePath`, указав каталог и имя. В этом примере объединяются строки `folderPath` и `fileName`, созданные в предыдущем примере, и отображается результат.  
  
     [!CODE [VbVbcnMyFileSystem#55](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#55)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>   
 <xref:System.IO.FileInfo>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>   
 [Практическое руководство. Получение коллекции содержащихся в каталоге файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)