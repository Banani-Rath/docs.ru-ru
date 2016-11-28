---
title: "Практическое руководство. Загрузка файла в Visual Basic | Microsoft Docs"
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
  - "загрузка файлов"
  - "загрузка ресурсов Интернета, файлы"
  - "файлы, загрузка"
  - "файлы, передача"
  - "удаленный компьютер, загрузка из"
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Загрузка файла в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Метод <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> можно использовать для загрузки удаленного файла и хранения его в заданном расположении.  Если параметр `ShowUI` имеет значение `True`, то отображается диалоговое окно, показывающее ход загрузки и позволяющее пользователю отменить операцию.  По умолчанию существующие файлы с тем же именем не перезаписываются; если требуется перезаписывать существующие файлы, установите для параметра `overwrite` значение `True`.  
  
 При следующих условиях возможно возникновение исключения.  
  
-   Имя диска является недопустимым \(<xref:System.ArgumentException>\).  
  
-   Необходимая проверка подлинности не обеспечена \(<xref:System.UnauthorizedAccessException> или <xref:System.Security.SecurityException>\).  
  
-   Сервер не отвечает в пределах указанного `connectionTimeout` \(<xref:System.TimeoutException>\).  
  
-   Запрос отклонен веб\-узлом \(<xref:System.Net.WebException>\).  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
> [!IMPORTANT]
>  По имени файла не всегда можно с уверенностью судить о его содержимом.  Например, файл с именем Form1.vb может и не являться исходным файлом Visual Basic.  Следует проверять все входные данные перед использованием их в приложении.  Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.  
  
### Загрузка файла  
  
-   Для загрузки файла используйте метод `DownloadFile`, указав расположение конечного файла в виде строки или URI и задав место, в котором будет сохранен файл.  В этом примере производится загрузка файла `WineList.txt` с веб\-узла `http://www.cohowinery.com/downloads` и сохранение его в каталоге `C:\Documents and Settings\All Users\Documents`:  
  
     [!CODE [VbResourceTasks#9](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#9)]  
  
### Загрузка файла с указанием времени ожидания  
  
-   Для загрузки файла используйте метод `DownloadFile`, задав расположение конечного файла в виде строки или URI, а также задав расположение хранения файла и продолжительность времени ожидания в миллисекундах \(по умолчанию 1 000 миллисекунд\).  В этом примере выполняется загрузка файла `WineList.txt` с веб\-сайта `http://www.cohowinery.com/downloads` с последующим сохранением в `C:\Documents and Settings\All Users\Documents`, при этом задается продолжительность времени ожидания 500 миллисекунд.  
  
     [!CODE [VbResourceTasks#10](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#10)]  
  
### Загрузка файла с указанием имени пользователя и пароля  
  
-   Для загрузки файла используйте метод `DownLoadFile`, указав расположение конечного файла в виде строки или URI, место, в котором будет сохранен файл, имя пользователя и пароль.  В данном примере производится загрузка файла `WineList.txt` с веб\-узла `http://www.cohowinery.com/downloads` и сохранение его в каталоге `C:\Documents and Settings\All Users\Documents`. Указывается имя пользователя `anonymous` и пустой пароль.  
  
     [!CODE [VbResourceTasks#11](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#11)]  
  
    > [!IMPORTANT]
    >  Протокол FTP, используемый в методе `DownLoadFile`, отправляет данные, включая пароли, в формате обычного текста и не должен использоваться для передачи важных сведений.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Network>   
 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>   
 [Практическое руководство. Выгрузка файла](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)   
 [Практическое руководство. Анализ путей к файлам](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)