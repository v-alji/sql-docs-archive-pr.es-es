---
title: Programa externo de Correo electrónico de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- external programs [Database Mail]
- DatabaseMail90.exe
- Database Mail [SQL Server], external programs
ms.assetid: bc124164-eb6e-4b7f-bf66-98a3113d02f7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 698fc8d97a565b4181552691a0260486c9c43bfd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751166"
---
# <a name="database-mail-external-program"></a><span data-ttu-id="22f37-102">Programa externo Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="22f37-102">Database Mail External Program</span></span>
  <span data-ttu-id="22f37-103">El ejecutable externo de Correo electrónico de base de datos es **DatabaseMail.exe**, que está ubicado en el directorio **MSSQL\Binn directory** de la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22f37-103">The Database Mail external executable is **DatabaseMail.exe**, located in the **MSSQL\Binn directory** of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="22f37-104">Correo electrónico de base de datos utiliza la activación de Service Broker para iniciar el programa externo cuando es necesario procesar mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="22f37-104">Database Mail uses Service Broker activation to start the external program when there are e-mail messages to be processed.</span></span> <span data-ttu-id="22f37-105">Correo electrónico de base de datos inicia una instancia del programa externo.</span><span class="sxs-lookup"><span data-stu-id="22f37-105">Database Mail starts one instance of the external program.</span></span> <span data-ttu-id="22f37-106">El programa externo se ejecuta en el contexto de seguridad de la cuenta de servicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22f37-106">The external program runs in the security context of the service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="22f37-107">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="22f37-107">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="22f37-108">Conceptos del programa externo de Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="22f37-108">Database Mail External Program Concepts</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="22f37-109">Tareas relacionadas con la configuración del programa externo de Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="22f37-109">Tasks Related to Configuring Database Mail External Program</span></span>](#RelatedTasks)  
  
##  <a name="database-mail-external-program-concepts"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="22f37-110">Conceptos del programa externo de Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="22f37-110">Database Mail External Program Concepts</span></span>  
 <span data-ttu-id="22f37-111">Cuando se inicia el programa externo, se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante la autenticación de Windows y empieza a procesar los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="22f37-111">When the external program starts, the program connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Windows Authentication and begins processing e-mail messages.</span></span> <span data-ttu-id="22f37-112">El programa termina cuando ya no hay mensajes para enviar durante el período de tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="22f37-112">When there have been no messages to send for the specified time-out period, the program exits.</span></span> <span data-ttu-id="22f37-113">Si lo desea, puede configurar el tiempo que el programa debe esperar antes de terminar mediante el Asistente para configuración de Correo electrónico de base de datos o los procedimientos almacenados de Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="22f37-113">You can configure the amount of time that the program waits before exiting by using either Database Mail Configuration Wizard or the Database Mail stored procedures.</span></span> <span data-ttu-id="22f37-114">Para obtener más información, vea [sysmail_configure_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="22f37-114">For more information, see [sysmail_configure_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql).</span></span>  
  
 <span data-ttu-id="22f37-115">El programa externo almacena información de las tablas del sistema en la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="22f37-115">The external program stores information in system tables in the **msdb** database.</span></span> <span data-ttu-id="22f37-116">Si el programa externo no puede comunicarse con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], registrará una serie de errores en el registro de eventos de aplicación de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="22f37-116">If the external program cannot communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the program logs errors to the Microsoft Windows application event log.</span></span> <span data-ttu-id="22f37-117">Se proporcionan funciones de registro de mensajes adicionales cuando el nivel de registro está establecido en **Detallado** en el cuadro de diálogo **Configurar parámetros del sistema** del **Asistente para configuración de Correo electrónico de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="22f37-117">Additional message logging is provided when the logging level is set to **Verbose** in the **Configure System Parameters** dialog box of the **Database Mail Configuration Wizard**.</span></span>  
  
 <span data-ttu-id="22f37-118">Por motivos de eficacia, el programa externo almacena en la memoria caché la información de la cuenta y del perfil.</span><span class="sxs-lookup"><span data-stu-id="22f37-118">Notice that, for efficiency, the external program caches account and profile information.</span></span> <span data-ttu-id="22f37-119">Por lo tanto, los cambios de configuración que se realicen en las cuentas y los perfiles no surtirán efecto en el programa externo hasta pasados unos minutos.</span><span class="sxs-lookup"><span data-stu-id="22f37-119">Therefore, configuration changes to accounts and profiles may not be reflected in the external program for a few minutes.</span></span>  
  
##  <a name="tasks-related-to-configuring-database-mail-external-program"></a><a name="RelatedTasks"></a> <span data-ttu-id="22f37-120">Tareas relacionadas con la configuración del programa externo de Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="22f37-120">Tasks Related to Configuring Database Mail External Program</span></span>  
  
|<span data-ttu-id="22f37-121">Tarea de configuración</span><span class="sxs-lookup"><span data-stu-id="22f37-121">Configuration Task</span></span>|<span data-ttu-id="22f37-122">Vínculo de tema</span><span class="sxs-lookup"><span data-stu-id="22f37-122">Topic Link</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="22f37-123">Especifique el tiempo que el programa externo espera antes de salir.</span><span class="sxs-lookup"><span data-stu-id="22f37-123">Specify the time that the External Program before exiting.</span></span>|[<span data-ttu-id="22f37-124">sysmail_configure_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="22f37-124">sysmail_configure_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql)|  
  
## <a name="see-also"></a><span data-ttu-id="22f37-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22f37-125">See Also</span></span>  
 <span data-ttu-id="22f37-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="22f37-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="22f37-127">[Registro y auditorías del Correo electrónico de base de datos](database-mail-log-and-audits.md) </span><span class="sxs-lookup"><span data-stu-id="22f37-127">[Database Mail Log and Audits](database-mail-log-and-audits.md) </span></span>  
 [<span data-ttu-id="22f37-128">Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="22f37-128">Database Mail</span></span>](database-mail.md)  
  
  
