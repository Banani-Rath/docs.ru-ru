---
title: "Пошаговое руководство. Управление файлами с помощью методов .NET Framework (Visual Basic) | Microsoft Docs"
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
  - "файлы, доступ"
  - "файлы, поиск"
  - "ввод-вывод [Visual Basic], чтение текста из файлов"
  - "ввод-вывод [Visual Basic], пошаговые руководства"
  - "ввод-вывод [Visual Basic], запись текста в файлы"
  - "чтение текстовых файлов"
  - "StreamReader - класс, пошаговые руководства"
  - "StreamWriter - класс, пошаговые руководства"
  - "текстовые файлы, чтение"
  - "текстовые файлы, запись в"
  - "текст, запись в файлы"
  - "запись в файлы, пошаговые руководства"
ms.assetid: 7d2109eb-f98a-4389-b43d-30f384aaa7d5
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Пошаговое руководство. Управление файлами с помощью методов .NET Framework (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В данном пошаговом руководстве демонстрируется открытие и чтение файла с помощью класса <xref:System.IO.StreamReader>, проверка факта доступа к файлу в настоящий момент, поиск строки в файле, считанном с помощью экземпляра класса <xref:System.IO.StreamReader>, и запись в файл с помощью класса <xref:System.IO.StreamWriter>.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## Создание приложения  
 Запустите [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] и начните проект с создания формы, которую пользователь сможет использовать для записи в намеченный файл.  
  
#### Создание проекта  
  
1.  В меню **Файл** выберите **Новый проект**.  
  
2.  В области **Новый проект** выберите **Приложение Windows**.  
  
3.  В окне **Имя** введите `MyDiary` и нажмите кнопку **ОК**.  
  
     [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] добавит проект в **Обозреватель решений**, и откроется **Конструктор Windows Forms**.  
  
4.  Добавьте в форму элементы управления из следующей таблицы и установите для их свойств соответствующие значения.  
  
||||  
|-|-|-|  
|**Объект.**|**Свойства**|**Значение**|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**|`Подтвердить`<br /><br /> Сохранить запись|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**|`Очистить`<br /><br /> Очистить запись|  
|<xref:System.Windows.Forms.TextBox>|**Имя**<br /><br /> **Текст**<br /><br /> **Multiline**|`Entry`<br /><br /> Введите произвольный текст.<br /><br /> `False`|  
  
## Запись в файл  
 Чтобы добавить возможность записи в файл с помощью этого приложения, воспользуйтесь классом <xref:System.IO.StreamWriter>.  Класс <xref:System.IO.StreamWriter> разработан для вывода символов в определенной кодировке, тогда как класс <xref:System.IO.Stream> разработан для ввода и вывода байтов.  Класс <xref:System.IO.StreamWriter> следует использовать для записи строк данных в стандартный текстовый файл.  Дополнительные сведения о классе <xref:System.IO.StreamWriter> см. в разделе <xref:System.IO.StreamWriter>.  
  
#### Добавление возможности записи  
  
1.  В меню **Вид** выберите **Код**, чтобы открыть редактор кода.  
  
2.  Поскольку приложение ссылается на пространство имен <xref:System.IO>, необходимо добавить следующие операторы в самом начале кода, перед объявлением класса формы, которое начинается с `Public Class Form1`.  
  
     [!CODE [VbVbcnMyFileSystem#35](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#35)]  
  
     Перед записью в файл необходимо создать экземпляр класса <xref:System.IO.StreamWriter>.  
  
3.  В меню **Вид** выберите **Конструктор** чтобы вернуться в окно **Конструктор Windows Forms**.  Чтобы создать обработчик событий <xref:System.Windows.Forms.Control.Click>, необходимо дважды щелкнуть кнопку `Submit` и затем добавить следующий код:  
  
     [!CODE [VbVbcnMyFileSystem#36](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#36)]  
  
> [!NOTE]
>  Произойдет возврат в редактор кода Visual Studio, а курсор будет помещен внутрь обработчика события, в который и следует добавить код.  
  
1.  Для записи в файл используйте метод <xref:System.IO.StreamWriter.Write%2A> класса <xref:System.IO.StreamWriter>.  Добавьте следующий код сразу после `Dim fw As StreamWriter`.  Не стоит беспокоиться о том, что возникнет исключение, если файла не существует, т. к. в этом случае он будет создан автоматически.  
  
     [!CODE [VbVbcnMyFileSystem#37](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#37)]  
  
2.  Чтобы убедиться, что пользователь не сможет отправить пустую запись, можно добавить следующий код сразу после `Dim ReadString As String`.  
  
     [!CODE [VbVbcnMyFileSystem#38](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#38)]  
  
3.  Поскольку речь идет о дневнике, пользователь захочет добавить к каждой записи дату.  Вставьте следующий код после `fw = New StreamWriter("C:\MyDiary.txt", True)`, чтобы присвоить переменной `Today` значение текущей даты.  
  
     [!CODE [VbVbcnMyFileSystem#39](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#39)]  
  
4.  В заключение добавьте код, очищающий элемент управления <xref:System.Windows.Forms.TextBox>.  Добавьте следующий код к событию <xref:System.Windows.Forms.Control.Click> кнопки `Clear`.  
  
     [!CODE [VbVbcnMyFileSystem#40](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#40)]  
  
## Добавление средств отображения в дневник  
 В этом разделе добавляется средство для отображения последней записи в элементе управления `DisplayEntry` <xref:System.Windows.Forms.TextBox>.  Можно также добавить элемент управления <xref:System.Windows.Forms.ComboBox>, в котором будут отображаться различные записи и из которого пользователь сможет выбрать запись для отображения в элементе управления `DisplayEntry` <xref:System.Windows.Forms.TextBox>.  Экземпляр класса <xref:System.IO.StreamReader> производит чтение из файла `MyDiary.txt`.  Как и <xref:System.IO.StreamWriter>, класс <xref:System.IO.StreamReader> предназначен для работы с текстовыми файлами.  
  
 Для реализации следующей части пошагового руководства необходимо добавить в форму элементы управления из следующей таблицы и присвоить соответствующие значения их свойствам.  
  
|Элемент управления|Свойства|Значения|  
|------------------------|--------------|--------------|  
|<xref:System.Windows.Forms.TextBox>|**Имя**<br /><br /> **Visible**<br /><br /> **Размер**<br /><br /> **Multiline**|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**|`Отображение`<br /><br /> Отображение|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**|`GetEntries`<br /><br /> Показать записи|  
|<xref:System.Windows.Forms.ComboBox>|**Имя**<br /><br /> **Текст**<br /><br /> **Enabled**|`PickEntries`<br /><br /> Выберите запись<br /><br /> `False`|  
  
#### Заполнение элемента управления ComboBox  
  
1.  В элементе управления `PickEntries` <xref:System.Windows.Forms.ComboBox> отображается дата создания каждой из записей, чтобы пользователь мог выбрать запись за определенную дату.  Создайте обработчик событий <xref:System.Windows.Forms.Control.Click> кнопки `GetEntries` и добавьте следующий код.  
  
     [!CODE [VbVbcnMyFileSystem#41](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#41)]  
  
2.  Чтобы удостовериться в работоспособности кода, нажмите клавишу F5 для компиляции приложения, а затем кнопку **Показать записи**.  Щелкните стрелку элемента управления <xref:System.Windows.Forms.ComboBox>, чтобы просмотреть даты создания всех записей.  
  
#### Выбор и просмотр отдельных записей  
  
1.  Создайте обработчик событий <xref:System.Windows.Forms.Control.Click> на кнопку `Display` и добавьте следующий код.  
  
     [!CODE [VbVbcnMyFileSystem#42](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#42)]  
  
2.  Чтобы удостовериться в работоспособности кода, нажмите клавишу F5 для компиляции приложения и введите запись.  Нажмите кнопку **Показать записи**, выберите запись в элементе управления <xref:System.Windows.Forms.ComboBox>, а затем нажмите кнопку **Просмотреть**.  Содержимое выбранной записи будет отображено в элементе управления `DisplayEntry` <xref:System.Windows.Forms.TextBox>.  
  
## Предоставление пользователям возможности удалять и изменять записи  
 В заключение можно снабдить приложение дополнительными функциями, позволяющими пользователю удалять и изменять записи с помощью кнопок `DeleteEntry` и `EditEntry`.  Обе кнопки неактивны, пока не выбрана ни одна запись.  
  
 Добавьте в форму элементы управления из следующей таблицы и установите для их свойств соответствующие значения.  
  
|Элемент управления|Свойства|Значения|  
|------------------------|--------------|--------------|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**<br /><br /> **Enabled**|`DeleteEntry`<br /><br /> Удалить запись<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**<br /><br /> **Enabled**|`EditEntry`<br /><br /> Изменить запись<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**<br /><br /> **Enabled**|`SubmitEdit`<br /><br /> Сохранить изменения<br /><br /> `False`|  
  
#### Включение возможности удаления и изменения записей  
  
1.  Добавьте следующий код к событию <xref:System.Windows.Forms.Control.Click> кнопки `Display` после `DisplayEntry.Text = ReadString`.  
  
     [!CODE [VbVbcnMyFileSystem#43](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#43)]  
  
2.  Создайте обработчик событий <xref:System.Windows.Forms.Control.Click> кнопки `DeleteEntry` и добавьте следующий код.  
  
     [!CODE [VbVbcnMyFileSystem#44](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#44)]  
  
3.  Когда пользователь отображает запись, кнопка `EditEntry` становится доступной.  Добавьте следующий код к событию <xref:System.Windows.Forms.Control.Click> кнопки `Display` после `DisplayEntry.Text = ReadString`.  
  
     [!CODE [VbVbcnMyFileSystem#45](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#45)]  
  
4.  Создайте обработчик событий <xref:System.Windows.Forms.Control.Click> кнопки `EditEntry` и добавьте следующий код.  
  
     [!CODE [VbVbcnMyFileSystem#46](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#46)]  
  
5.  Создайте обработчик событий <xref:System.Windows.Forms.Control.Click> кнопки `SubmitEdit` и добавьте следующий код.  
  
     [!CODE [VbVbcnMyFileSystem#47](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#47)]  
  
 Чтобы удостовериться в работоспособности кода, нажмите клавишу F5 для компиляции приложения.  Нажмите кнопку **Показать записи**, выберите запись и нажмите кнопку **Просмотреть**.  Запись будет отображена в элементе управления `DisplayEntry` <xref:System.Windows.Forms.TextBox>.  Нажмите кнопку **Изменить запись**.  Запись будет отображена в элементе управления `Entry` <xref:System.Windows.Forms.TextBox>.  Отредактируйте запись в элементе управления `Entry` <xref:System.Windows.Forms.TextBox> и нажмите кнопку **Сохранить изменения**.  Откройте файл `MyDiary.txt`, чтобы убедиться в том, что исправления внесены.  Теперь выберите запись и нажмите кнопку **Удалить запись**.  Когда появится окно сообщения <xref:System.Windows.Forms.MessageBox> с запросом подтверждения, нажмите кнопку **ОК**.  Закройте приложение и откройте файл `MyDiary.txt`, чтобы убедиться, что запись была удалена.  
  
## См. также  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.StreamWriter>   
 [Пошаговые руководства](../../../../visual-basic/walkthroughs.md)