---
title: c2 audit mode (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], C2 Audit Mode option
- C2 auditing
- C2 Audit Mode option
- recording attempts
ms.assetid: 5a8d73a6-c4f6-4967-ba11-ecbcfc90b9cc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3407a2a94a43adb2d3d3b52994093d6ed0c2e684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749475"
---
# <a name="c2-audit-mode-server-configuration-option"></a><span data-ttu-id="c95da-102">c2 audit mode (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="c95da-102">c2 audit mode Server Configuration Option</span></span>
  <span data-ttu-id="c95da-103">El modo auditoría C2 puede configurarse mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o con la opción **Modo auditoría C2** de **sp_configure**.</span><span class="sxs-lookup"><span data-stu-id="c95da-103">C2 audit mode can be configured through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or with the **c2 audit mode** option in **sp_configure**.</span></span> <span data-ttu-id="c95da-104">Al seleccionar esta opción, el servidor registrará tanto los intentos sin éxito como los intentos con éxito de acceso a instrucciones y objetos.</span><span class="sxs-lookup"><span data-stu-id="c95da-104">Selecting this option will configure the server to record both failed and successful attempts to access statements and objects.</span></span> <span data-ttu-id="c95da-105">Esta información puede servirle de ayuda para perfilar la actividad del sistema y realizar un seguimiento de las posibles infracciones de las directivas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c95da-105">This information can help you profile system activity and track possible security policy violations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="c95da-106">El estándar de seguridad C2 se ha sustituido por Common Criteria Certification.</span><span class="sxs-lookup"><span data-stu-id="c95da-106">The C2 security standard has been superseded by Common Criteria Certification.</span></span> <span data-ttu-id="c95da-107">Vea [common criteria compliance enabled (opción de configuración del servidor)](common-criteria-compliance-enabled-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="c95da-107">See the [common criteria compliance enabled Server Configuration Option](common-criteria-compliance-enabled-server-configuration-option.md).</span></span>  
  
## <a name="audit-log-file"></a><span data-ttu-id="c95da-108">Archivo de registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="c95da-108">Audit Log File</span></span>  
 <span data-ttu-id="c95da-109">Los datos del modo auditoría C2 se guardan en un archivo en el directorio de datos predeterminado de la instancia.</span><span class="sxs-lookup"><span data-stu-id="c95da-109">C2 audit mode data is saved in a file in the default data directory of the instance.</span></span> <span data-ttu-id="c95da-110">Si el tamaño del archivo de registro de auditoría supera el límite de 200 megabytes (MB), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creará un archivo nuevo, cerrará el antiguo y escribirá todos los registros de auditoría nuevos en el nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="c95da-110">If the audit log file reaches its size limit of 200 megabytes (MB), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will create a new file, close the old file, and write all new audit records to the new file.</span></span> <span data-ttu-id="c95da-111">Este proceso continuará hasta que el directorio de datos de auditoría se llene o la función de auditoría se desactive.</span><span class="sxs-lookup"><span data-stu-id="c95da-111">This process will continue until the audit data directory fills up or auditing is turned off.</span></span> <span data-ttu-id="c95da-112">Para determinar el estado de un seguimiento de C2, consulte la vista de catálogo sys.traces.</span><span class="sxs-lookup"><span data-stu-id="c95da-112">To determine the status of a C2 trace, query the sys.traces catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c95da-113">El modo auditoría C2 guarda una gran cantidad de información de eventos en el archivo de registro, por lo que puede crecer rápidamente.</span><span class="sxs-lookup"><span data-stu-id="c95da-113">C2 audit mode saves a large amount of event information to the log file, which can grow quickly.</span></span> <span data-ttu-id="c95da-114">Si el directorio de datos en el que se guardan los registros se queda sin espacio, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se cerrará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c95da-114">If the data directory in which logs are being saved runs out of space, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will shut itself down.</span></span> <span data-ttu-id="c95da-115">Si la auditoría se ha configurado para iniciarse automáticamente, deberá reiniciar la instancia con la marca **-f** (que omite la auditoría) o liberar más espacio en disco para el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="c95da-115">If auditing is set to start automatically, you must either restart the instance with the **-f** flag (which bypasses auditing), or free up additional disk space for the audit log.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="c95da-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="c95da-116">Permissions</span></span>  
 <span data-ttu-id="c95da-117">Requiere la pertenencia al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c95da-117">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c95da-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c95da-118">Example</span></span>  
 <span data-ttu-id="c95da-119">El ejemplo siguiente activa el modo auditoría C2.</span><span class="sxs-lookup"><span data-stu-id="c95da-119">The following example turns on C2 audit mode.</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
sp_configure 'c2 audit mode', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="c95da-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c95da-120">See Also</span></span>  
 <span data-ttu-id="c95da-121">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c95da-121">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="c95da-122">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c95da-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="c95da-123">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c95da-123">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
