---
title: Comprobación del estado de los mensajes de correo electrónico enviados con Correo electrónico de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- e-mail [SQL Server], status information
- mail [SQL Server], status information
- Database Mail [SQL Server], message status
- status information [Database Mail]
ms.assetid: eb290f24-b52f-46bc-84eb-595afee6a5f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1642c456cd64484dede64f8127ff2f979f2242e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677666"
---
# <a name="check-the-status-of-e-mail-messages-sent-with-database-mail"></a><span data-ttu-id="0a422-102">Comprobar el estado de los mensajes de correo electrónico enviados con Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="0a422-102">Check the Status of E-Mail Messages Sent With Database Mail</span></span>
  <span data-ttu-id="0a422-103">En este tema se describe cómo comprobar el estado del mensaje de correo electrónico enviado con Correo electrónico de base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a422-103">This topic describes how to check the status of the e-mail message sent using Database Mail  in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="0a422-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="0a422-104">**Before you begin:**</span></span>  
  
-   <span data-ttu-id="0a422-105">**Para ver el estado del correo electrónico enviado con Correo electrónico de base de datos, mediante:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="0a422-105">**To view the status of the e-mail sent using Database Mail, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0a422-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="0a422-106">Before You Begin</span></span>  
 <span data-ttu-id="0a422-107">Correo electrónico de base de datos conserva copias de los mensajes de correo electrónico salientes y las muestra en las vistas **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**y **sysmail_faileditems** de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="0a422-107">Database Mail keeps copies of outgoing e-mail messages and displays them in the **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**, **sysmail_faileditems** views of the **msdb** database.</span></span> <span data-ttu-id="0a422-108">El programa externo de Correo electrónico de base de datos registra la actividad y muestra ese registro por medio del registro de eventos de aplicación Windows y la vista **sysmail_event_log** de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="0a422-108">The Database Mail external program logs activity and displays the log through the Windows Application Event Log and the **sysmail_event_log** view in the **msdb** database.</span></span> <span data-ttu-id="0a422-109">Para comprobar el estado de un mensaje de correo electrónico, ejecute una consulta en esta vista.</span><span class="sxs-lookup"><span data-stu-id="0a422-109">To check the status of an e-mail message, run a query against this view.</span></span> <span data-ttu-id="0a422-110">Los mensajes de correo electrónico tienen cuatro posibles estados: **enviado**, **no enviado**, **reintentando**y **error**.</span><span class="sxs-lookup"><span data-stu-id="0a422-110">E-mail messages have one of four possible statuses: **sent**, **unsent**, **retrying**, and **failed**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0a422-111">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a422-111">Using Transact-SQL</span></span>  
 <span data-ttu-id="0a422-112">**Para ver el estado del correo electrónico enviado con Correo electrónico de base de datos**</span><span class="sxs-lookup"><span data-stu-id="0a422-112">**To view the status of the e-mail sent using Database Mail**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a422-113">Para ver un ejemplo de este procedimiento, vea [Ejemplo (Transact-SQL)](#TsqlExample)más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="0a422-113">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="0a422-114">Seleccione los mensajes que le interesen de la tabla **sysmail_allitems** por medio de **mailitem_id** o **sent_status**.</span><span class="sxs-lookup"><span data-stu-id="0a422-114">Select from the **sysmail_allitems** table, specifying the messages of interest by **mailitem_id** or **sent_status**.</span></span>  
  
2.  <span data-ttu-id="0a422-115">Para comprobar el estado devuelto por el programa externo para los mensajes de correo electrónico, combine las vistas **sysmail_allitems** y **sysmail_event_log** en la columna **mailitem_id** , como se muestra en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="0a422-115">To check the status returned from the external program for the e-mail messages, join **sysmail_allitems** to **sysmail_event_log** view on the **mailitem_id** column, as shown in the following section.</span></span>  
  
     <span data-ttu-id="0a422-116">De forma predeterminada, el programa externo no registra información acerca de los mensajes que se enviaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="0a422-116">By default, the external program does not log information about messages that were successfully sent.</span></span> <span data-ttu-id="0a422-117">Para registrar todos los mensajes, establezca el nivel de registro en detallado mediante la página **Configurar parámetros del sistema** del **Asistente para configuración de Correo electrónico de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="0a422-117">To log all messages, set the logging level to verbose using the **Configure System Parameters** page of the **Database Mail Configuration Wizard.**</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="0a422-118">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0a422-118">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="0a422-119">En el siguiente ejemplo se muestra información acerca de los mensajes de correo electrónico enviados a `danw` que el programa externo no ha podido enviar correctamente.</span><span class="sxs-lookup"><span data-stu-id="0a422-119">The following example lists information about any e-mail messages sent to `danw` that the external program could not send successfully.</span></span> <span data-ttu-id="0a422-120">La instrucción incluye el asunto, la fecha y la hora en que el programa externo no pudo enviar el mensaje, así como el mensaje de error del registro de Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0a422-120">The statement lists the subject, the date and time that the external program failed to send the message, and the error message from the Database Mail log.</span></span>  
  
```  
USE msdb ;  
GO  
  
-- Show the subject, the time that the mail item row was last  
-- modified, and the log information.  
-- Join sysmail_faileditems to sysmail_event_log   
-- on the mailitem_id column.  
-- In the WHERE clause list items where danw was in the recipients,  
-- copy_recipients, or blind_copy_recipients.  
-- These are the items that would have been sent  
-- to danw.  
  
SELECT items.subject,  
    items.last_mod_date  
    ,l.description FROM dbo.sysmail_faileditems as items  
INNER JOIN dbo.sysmail_event_log AS l  
    ON items.mailitem_id = l.mailitem_id  
WHERE items.recipients LIKE '%danw%'    
    OR items.copy_recipients LIKE '%danw%'   
    OR items.blind_copy_recipients LIKE '%danw%'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a422-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a422-121">See Also</span></span>  
 [<span data-ttu-id="0a422-122">Registro y auditorías del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="0a422-122">Database Mail Log and Audits</span></span>](database-mail-log-and-audits.md)  
  
  
