---
title: "Практическое руководство. Предоставление диалогового окна &quot;Ход выполнения&quot; для операций с файлами (Руководство по программированию на C#) | Microsoft Docs"
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
  - "ход выполнения - диалоговое окно [C#]"
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Предоставление диалогового окна &quot;Ход выполнения&quot; для операций с файлами (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Можно предоставить стандартное диалоговое окно, показывающее ход выполнения операций с файлами в Windows при использовании метода <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> в пространстве имен <xref:Microsoft.VisualBasic?displayProperty=fullName>.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Добавление ссылки в Visual Studio  
  
1.  В меню **Проект** выберите **Добавить ссылку**.  
  
     Появится диалоговое окно **Диспетчер ссылок**.  
  
2.  В области **Сборки** выберите **Framework**, если она еще не выбрана.  
  
3.  В списке имен выберите флажок **Microsoft.VisualBasic**, а затем нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
## Пример  
 В следующем коде каталог, указанный параметром `sourcePath`, копируется в каталог, указанный параметром `destinationPath`.  Этот код также предоставляет стандартное диалоговое окно, в котором показывается оценочное время, оставшееся до окончания операции.  
  
 [!CODE [csFilesandFolders#11](../CodeSnippet/VS_Snippets_VBCSharp/csFilesAndFolders#11)]  
  
## См. также  
 [Файловая система и реестр](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)