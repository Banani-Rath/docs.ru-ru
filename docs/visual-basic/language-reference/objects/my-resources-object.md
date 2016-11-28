---
title: "Объект My.Resources | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "My.Resources"
  - "My.Resources.MyResources.ResourceManager"
  - "My.Resources.MyResources.Culture"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Resources - объект"
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Объект My.Resources
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Предоставляет свойства и классы для доступа к ресурсам приложения.  
  
## Заметки  
 Объект `My.Resources` предоставляет доступ к ресурсам приложения и позволяет динамически извлекать ресурсы для приложения.  Дополнительные сведения см. в разделе [Управление ресурсами приложения \(.NET\)](/visual-studio/ide/managing-application-resources-dotnet).  
  
 Объект `My.Resources` предоставляет только глобальные ресурсы.  Он не обеспечивает доступа к файлам ресурсов, связанных с формами.  К ресурсам формы необходимо получать доступ из формы.  Дополнительные сведения см. в разделе [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 Можно получить доступ к файлам ресурсов приложения для определенного языка и региональных параметров из объекта `My.Resources`.  По умолчанию объект `My.Resources` ищет ресурсы в файле ресурсов, который соответствует языку и региональным параметрам, указанным в свойстве <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>.  Однако можно переопределить это поведение и указать для ресурсов определенный язык и региональные параметры.  Дополнительные сведения см. в разделе [Ресурсы в приложениях для настольных систем](../Topic/Resources%20in%20Desktop%20Apps.md).  
  
## Свойства  
 Свойства объекта `My.Resources` предоставляет доступ только для чтения к ресурсам приложения.  Чтобы добавить или удалить ресурсы, используйте **Конструктор проекта**.  Дополнительные сведения см. в разделе [How to: Add or Remove Resources](http://msdn.microsoft.com/ru-ru/7b77bc06-3952-4799-b029-def3f8f7f88d).  Можно получить доступ к ресурсам, добавленным с помощью **Конструктора проектов** с использованием `My.Resources.``resourceName`.  
  
 Можно также добавить или удалить файлы ресурсов, выбрав проект в **Обозревателе решений** и щелкнув **Добавление нового элемента** или  **Добавление существующего элемента**  в меню **Проект**.  Можно получить доступ к ресурсам, добавленным таким образом, с помощью `My.Resources.``resourceFileName`. `resourceName`.  
  
 Каждый ресурс имеет имя, категорию и значение. Эти параметры ресурсов определяют, как свойство доступа к ресурсу отображается в объекте `My.Resources`.  Для ресурсов, добавленных с помощью **Конструктора проектов**:  
  
-   Имя определяет имя свойства.  
  
-   Данные ресурсов являются значением свойства,  
  
-   Категория определяет тип свойства.  
  
|||  
|-|-|  
|Категория|Тип данных свойства|  
|**Строки**|[Строка.](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Изображения**|<xref:System.Drawing.Bitmap>|  
|**Значки**|<xref:System.Drawing.Icon>|  
|**Звук**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> Класс <xref:System.IO.UnmanagedMemoryStream> является производным от класса <xref:System.IO.Stream>, поэтому его можно использовать в методах, которые принимают потоки, таких как <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>.|  
|**Файлы**|-   [String](../../../visual-basic/language-reference/data-types/string-data-type.md) для текстовых файлов.<br />-   <xref:System.Drawing.Bitmap> для файлов изображений.<br />-   <xref:System.Drawing.Icon> для файлов значков.<br />-   <xref:System.IO.UnmanagedMemoryStream> для звуковых файлов.|  
|**Другой**|Определяются данными в столбце **Тип** конструктора.|  
  
## Классы  
 Объект `My.Resources` представляет каждый файл ресурсов как класс с общими свойствами.  Имя класса такое же, что и имя файла ресурсов.  Как описано в предыдущем разделе, ресурсы в файле ресурсов представляются свойствами в классе.  
  
## Пример  
 Этот пример задает заголовок формы к ресурсу строк называется `Form1Title` в файле ресурсов приложения.  Пример работал, приложение должно иметь строки `Form1Title` в файле ресурсов.  Дополнительные сведения см. в разделе [How to: Add or Remove Resources](http://msdn.microsoft.com/ru-ru/7b77bc06-3952-4799-b029-def3f8f7f88d).  
  
 [!CODE [VbVbalrMyResources#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyResources#1)]  
  
## Пример  
 В следующем примере значок формы меняется на значок с именем `Form1Icon`, хранящийся в файле ресурсов приложения.  Пример работал, приложение должно иметь именованный значок `Form1Icon` в файле ресурсов.  
  
 [!CODE [VbVbalrMyResources#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyResources#2)]  
  
## Пример  
 Этот пример устанавливает образом фоновое изображение формы к ресурсу образа называется `Form1Background`, который в файле ресурсов приложения.  Для работы этого примера необходимо, чтобы приложение должно иметь именованный ресурс образа `Form1Background` в файле ресурсов.  
  
 [!CODE [VbVbalrMyResources#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyResources#3)]  
  
## Пример  
 В этом примере воспроизводится звук, который хранится в виде звукового именованный ресурс `Form1Greeting` в файле ресурсов приложения.  Пример работал, приложение должно иметь звукового именованный ресурс `Form1Greeting` в файле ресурсов.  Метод `My.Computer.Audio.Play` доступен только для приложений Windows Forms.  
  
 [!CODE [VbVbalrMyResources#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyResources#4)]  
  
## Пример  
 В этом примере извлекается версия Французск\-языка и региональных параметров строкового ресурса приложения.  Ресурс называется `Message`.  Изменить язык и региональные параметры, `My.Resources` объект использует пример использует  <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 Для работы этого примера необходимо, чтобы приложение должно иметь строки `Message` в файле ресурсов и приложении иметь версию Французск\-языка и региональные параметры этого файла ресурсов, Resources.fr\-FR.resx.  Дополнительные сведения см. в разделе [How to: Add or Remove Resources](http://msdn.microsoft.com/ru-ru/7b77bc06-3952-4799-b029-def3f8f7f88d).  Если приложение не имеет версии Французск\-языка и региональные параметры файла ресурсов, `My.Resource` объект получает ресурс из файла ресурсов по умолчанию\-языка и региональных параметров.  
  
 [!CODE [VbVbalrMyResources#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyResources#10)]  
  
## См. также  
 [How to: Add or Remove Resources](http://msdn.microsoft.com/ru-ru/7b77bc06-3952-4799-b029-def3f8f7f88d)   
 [Управление ресурсами приложения \(.NET\)](/visual-studio/ide/managing-application-resources-dotnet)   
 [Ресурсы в приложениях для настольных систем](../Topic/Resources%20in%20Desktop%20Apps.md)   
 [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5)