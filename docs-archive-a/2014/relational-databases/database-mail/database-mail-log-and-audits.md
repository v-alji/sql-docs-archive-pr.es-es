---
title: Registro y auditorías del Correo electrónico de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- Database Mail [SQL Server], auditing
- logs [Database Mail]
- audits [SQL Server], Database Mail
- Database Mail [SQL Server], logging
ms.assetid: 846589ee-5fe5-4ab3-b335-0c253e569f99
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6267389f187b955982ec1c18c411f703b4562f3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751150"
---
# <a name="database-mail-log-and-audits"></a><span data-ttu-id="66641-102">Registro y auditorías del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="66641-102">Database Mail Log and Audits</span></span>
  <span data-ttu-id="66641-103">La funcionalidad de registro del Correo electrónico de base de datos está diseñado para proporcionar una manera de aislar y de corregir problemas.</span><span class="sxs-lookup"><span data-stu-id="66641-103">The Database Mail logging functionality is designed to provide a way to isolate and correct problems.</span></span> <span data-ttu-id="66641-104">El Correo electrónico de base de datos almacena información de registro en la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="66641-104">Database Mail stores the log information in the **msdb** database.</span></span> <span data-ttu-id="66641-105">La información acerca del contenido del correo electrónico de base de datos, el estado de los mensajes, y cualquier mensaje recibido, como errores, está registrada por el Correo electrónico de base de datos y se puede usar para solucionar problemas y auditar ordenación.</span><span class="sxs-lookup"><span data-stu-id="66641-105">Information about Database Mail e-mail content, status of e-mails, and any messages received, such as errors  are logged by Database Mail and can be used for troubleshooting and auditing purposes.</span></span>  
  
## <a name="database-mail-logs"></a><span data-ttu-id="66641-106">Registros de Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="66641-106">Database Mail Logs</span></span>  
 <span data-ttu-id="66641-107">Tablas en la información de registro de la base de datos **msdb** de [Database Mail External Program](database-mail-external-program.md).</span><span class="sxs-lookup"><span data-stu-id="66641-107">Tables in the **msdb** database log information from the [Database Mail External Program](database-mail-external-program.md).</span></span> <span data-ttu-id="66641-108">[Vistas del Correo electrónico de base de datos &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql) expone las tablas para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="66641-108">[Database Mail Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql) expose the tables for troubleshooting purposes.</span></span> <span data-ttu-id="66641-109">Aparecen errores en la vista [sysmail_event_log &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) si Service Broker no puede activar el programa externo, si el programa externo encuentra errores de red o si el servidor SMTP (protocolo simple de transferencia de correo) rechaza un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="66641-109">Errors appear in the [sysmail_event_log &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) view if Service Broker cannot activate the external program, if the external program encounters networking errors or if the Simple Mail Transport Protocol (SMTP) server refuses an e-mail message.</span></span> <span data-ttu-id="66641-110">Si el programa externo no puede conectarse a las tablas **msdb** , el programa registra los errores en el registro de eventos de aplicación Windows.</span><span class="sxs-lookup"><span data-stu-id="66641-110">In the event that the external program cannot log to the **msdb** tables, the program logs errors to the Windows application event log.</span></span>  
  
 <span data-ttu-id="66641-111">Las tablas internas de la base de datos **msdb** contienen los mensajes de correo electrónico y los datos adjuntos enviados desde el Correo electrónico de base de datos, junto con el estado actual de cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="66641-111">Internal tables in the **msdb** database contain the e-mail messages and attachments sent from Database Mail, together with the current status of each message.</span></span> <span data-ttu-id="66641-112">El Correo electrónico de base de datos actualiza estas tablas a medida que se procesa cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="66641-112">Database Mail updates these tables as each message is processed.</span></span>  
  
## <a name="database-mail-auditing-tasks"></a><span data-ttu-id="66641-113">Tareas de auditoría de Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="66641-113">Database Mail Auditing tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66641-114">**Revisar y administrar los registros de Correo electrónico de base de datos**</span><span class="sxs-lookup"><span data-stu-id="66641-114">**Reviewing and managing Database Mail logs**</span></span>|<span data-ttu-id="66641-115">**Vínculo a tema**</span><span class="sxs-lookup"><span data-stu-id="66641-115">**Link to Topic**</span></span>|  
|<span data-ttu-id="66641-116">Comprobar el estado de entrega de un mensaje individual</span><span class="sxs-lookup"><span data-stu-id="66641-116">Check the delivery status of an individual message</span></span>|[<span data-ttu-id="66641-117">Comprobar el estado de los mensajes de correo electrónico enviados con Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="66641-117">Check the Status of E-Mail Messages Sent With Database Mail</span></span>](check-the-status-of-e-mail-messages-sent-with-database-mail.md)|  
|<span data-ttu-id="66641-118">Limpiar los mensajes, los datos adjuntos, y las entradas de registro del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="66641-118">Clean up Database Mail messages, attachments, and log entries</span></span>|[<span data-ttu-id="66641-119">sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="66641-119">sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-mailitems-sp-transact-sql)<br /><br /> [<span data-ttu-id="66641-120">sysmail_delete_log_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="66641-120">sysmail_delete_log_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-log-sp-transact-sql)|  
|<span data-ttu-id="66641-121">Almacenar los mensajes de correo electrónico y los registros de la base de datos</span><span class="sxs-lookup"><span data-stu-id="66641-121">Archive the Database Email Messages and Logs</span></span>|[<span data-ttu-id="66641-122">Crear un trabajo del Agente SQL Server para archivar mensajes y registros de eventos del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="66641-122">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>](create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="66641-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66641-123">See Also</span></span>  
 [<span data-ttu-id="66641-124">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="66641-124">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](../performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
