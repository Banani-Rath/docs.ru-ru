---
title: "Пошаговое руководство. Изменение места записи информации для My.Application.Log (Visual Basic) | Microsoft Docs"
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
  - "объект My.Application.Log, пошаговые руководства"
  - "журналы событий, изменение расположения вывода"
ms.assetid: ecc74f95-743c-450d-93f6-09a30db0fe4a
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Пошаговое руководство. Изменение места записи информации для My.Application.Log (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении. В этом пошаговом руководстве показано, как переопределить параметры по умолчанию и настроить объект `Log` на запись в другие прослушиватели журналов.  
  
## Обязательные компоненты  
 Объект `Log` может записывать информацию в несколько прослушивателей журналов. Перед изменением конфигурации необходимо определить текущую конфигурацию прослушивателей журналов. Для получения дополнительной информации см. [Пошаговое руководство. Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).  
  
 Возможно, будет полезно ознакомиться с разделами [Практическое руководство. Запись сведений о событиях в текстовый файл](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) и [Практическое руководство. Запись в журнал событий приложения](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md).  
  
### Добавление прослушивателей  
  
1.  Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.  
  
     \-или\-  
  
     Если файл app.config отсутствует, выполните указанные ниже действия.  
  
    1.  В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
    2.  В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.  
  
    3.  Нажмите кнопку **Добавить**.  
  
2.  Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name`, равным DefaultSource, в разделе `<sources>`. Раздел `<sources>` находится в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.  
  
3.  Добавьте в этот раздел `<listeners>` следующие элементы.  
  
    ```  
    <!-- Uncomment to connect the application file log. -->  
    <!-- <add name="FileLog" /> -->  
    <!-- Uncomment to connect the event log. -->  
    <!-- <add name="EventLog" /> -->  
    <!-- Uncomment to connect the event log. -->  
    <!-- <add name="Delimited" /> -->  
    <!-- Uncomment to connect the XML log. -->  
    <!-- <add name="XmlWriter" /> -->  
    <!-- Uncomment to connect the console log. -->  
    <!-- <add name="Console" /> -->  
    ```  
  
4.  Раскомментируйте прослушиватели журналов, которые должны получать сообщения `Log`.  
  
5.  Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.  
  
6.  Добавьте в этот раздел `<sharedListeners>` следующие элементы.  
  
    ```  
    <add name="FileLog"  
         type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
               Microsoft.VisualBasic, Version=8.0.0.0,   
               Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"  
         initializeData="FileLogWriter" />  
    <add name="EventLog"  
         type="System.Diagnostics.EventLogTraceListener,   
               System, Version=2.0.0.0,   
               Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="sample application"/>  
    <add name="Delimited"   
         type="System.Diagnostics.DelimitedListTraceListener,   
               System, Version=2.0.0.0,   
               Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="c:\temp\sampleDelimitedFile.txt"  
         traceOutputOptions="DateTime" />  
    <add name="XmlWriter"  
         type="System.Diagnostics.XmlWriterTraceListener,   
               System, Version=2.0.0.0,   
               Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="c:\temp\sampleLogFile.xml" />  
    <add name="Console"  
         type="System.Diagnostics.ConsoleTraceListener,   
               System, Version=2.0.0.0,   
               Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="true" />  
    ```  
  
7.  Содержимое файла app.config должно быть похоже на следующий код XML:  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
              <!-- Uncomment to connect the application file log. -->  
              <!-- <add name="FileLog" /> -->  
              <!-- Uncomment to connect the event log. -->  
              <!-- <add name="EventLog" /> -->  
              <!-- Uncomment to connect the event log. -->  
              <!-- <add name="Delimited" /> -->  
              <!-- Uncomment to connect the XML log. -->  
              <!-- <add name="XmlWriter" /> -->  
              <!-- Uncomment to connect the console log. -->  
              <!-- <add name="Console" /> -->  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="Information" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"  
               initializeData="FileLogWriter" />  
          <add name="EventLog"  
               type="System.Diagnostics.EventLogTraceListener,   
                     System, Version=2.0.0.0,   
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"  
               initializeData="sample application"/>  
          <add name="Delimited"   
               type="System.Diagnostics.DelimitedListTraceListener,   
                     System, Version=2.0.0.0,   
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"  
               initializeData="c:\temp\sampleDelimitedFile.txt"  
               traceOutputOptions="DateTime" />  
          <add name="XmlWriter"  
               type="System.Diagnostics.XmlWriterTraceListener,   
                     System, Version=2.0.0.0,   
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"  
               initializeData="c:\temp\sampleLogFile.xml" />  
          <add name="Console"  
               type="System.Diagnostics.ConsoleTraceListener,   
                     System, Version=2.0.0.0,   
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"  
               initializeData="true" />  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
### Перенастройка прослушивателя  
  
1.  Найдите элемент `<add>` прослушивателя из раздела `<sharedListeners>`.  
  
2.  Атрибут `type` содержит имя типа прослушивателя. Этот тип должен наследоваться от класса <xref:System.Diagnostics.TraceListener>. Используйте строгое имя типа, чтобы гарантировать, что используется верный тип. Дополнительные сведения см. в разделе "Создание ссылки на строго именованный тип" ниже.  
  
     Вот некоторые типы, которые можно использовать:  
  
    -   прослушиватель <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName>, ведущий запись в журнал файлов;  
  
    -   прослушиватель <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>, записывающий информацию в журнал событий компьютера, заданный параметром `initializeData`;  
  
    -   прослушиватели <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> и <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName>, ведущие запись в файл, указанный в параметре `initializeData`;  
  
    -   прослушиватель <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName>, ведущий запись в консоль командной строки.  
  
     Сведения о том, куда записывают информацию другие типы прослушивателей журналов, приведены в документации по этим типам.  
  
3.  Когда приложение создает объект прослушивателя журнала, оно передает атрибут `initializeData` в качестве параметра конструктора. Значение атрибута `initializeData` зависит от прослушивателя трассировки.  
  
4.  После создания прослушивателя журнала приложение задает его свойства. Эти свойства определяются другими атрибутами в элементе `<add>`. Дополнительные сведения о свойствах конкретного прослушивателя см. в документации к соответствующему типу прослушивателя.  
  
### Создание ссылки на строго именованный тип  
  
1.  Чтобы гарантировать, что для прослушивателя журнала используется правильный тип, убедитесь в том, что используется полное имя типа и строгое имя сборки. Синтаксис строго именованного типа выглядит следующим образом:  
  
     \<*имя типа*\>, \<*имя сборки*\>, \<*номер версии*\>, \<*язык и региональные параметры*\>, \<*строгое имя*\>  
  
2.  В этом примере кода показано, как определить строгое имя для типа с полным именем System.Diagnostics.FileLogTraceListener.  
  
     [!CODE [VbVbalrMyApplicationLog#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#15)]  
  
     Это выходные данные, и они могут использоваться для уникальной ссылки на строго именованный тип, как показано выше в процедуре "Добавление прослушивателей".  
  
     `Microsoft.VisualBasic.Logging.FileLogTraceListener, Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`  
  
## См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:System.Diagnostics.TraceListener>   
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName>   
 <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>   
 [Практическое руководство. Запись сведений о событиях в текстовый файл](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)   
 [Практическое руководство. Запись в журнал событий приложения](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)