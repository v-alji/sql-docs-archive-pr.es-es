---
title: Ver un registro de SQL Server Audit | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- audits [SQL Server], viewing logs
- viewing audit logs
- logs [SQL Server], audit
ms.assetid: e8feaca0-7852-422b-895a-319b965d8d9b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 8f9902a4fc92ef0b35bae62eb80170762c52fdec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669568"
---
# <a name="view-a-sql-server-audit-log"></a><span data-ttu-id="39e71-102">Ver un registro de SQL Server Audit</span><span class="sxs-lookup"><span data-stu-id="39e71-102">View a SQL Server Audit Log</span></span>
  <span data-ttu-id="39e71-103">Este tema describe cómo ver un registro de auditoría de SQL Server en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39e71-103">This topic describes how to view a SQL Server audit log in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="39e71-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="39e71-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="39e71-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="39e71-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="39e71-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="39e71-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="39e71-107">**Para ver un registro de auditoría de SQL Server, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="39e71-107">**To view a SQL Server audit log, using:**</span></span>  
  
     [<span data-ttu-id="39e71-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39e71-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="39e71-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="39e71-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="39e71-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="39e71-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="39e71-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="39e71-111">Permissions</span></span>  
 <span data-ttu-id="39e71-112">Requiere el permiso `CONTROL SERVER`.</span><span class="sxs-lookup"><span data-stu-id="39e71-112">Requires the `CONTROL SERVER` permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="39e71-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39e71-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-sql-server-audit-log"></a><span data-ttu-id="39e71-114">Para ver un registro de auditoría de SQL Server</span><span class="sxs-lookup"><span data-stu-id="39e71-114">To view a SQL Server audit log</span></span>  
  
1.  <span data-ttu-id="39e71-115">En el Explorador de objetos, expanda la carpeta **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="39e71-115">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="39e71-116">Expanda la carpeta **Auditorías** .</span><span class="sxs-lookup"><span data-stu-id="39e71-116">Expand the **Audits** folder.</span></span>  
  
3.  <span data-ttu-id="39e71-117">Haga clic con el botón derecho en el registro de auditoría que quiera ver y seleccione **Ver registros de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="39e71-117">Right-click the audit log that you want to view and select **View Audit Logs**.</span></span> <span data-ttu-id="39e71-118">Se abrirá el cuadro **de diálogo Visor del archivo de registros-**_SERVER_NAME_ .</span><span class="sxs-lookup"><span data-stu-id="39e71-118">This opens the **Log File Viewer -**_server_name_ dialog box.</span></span> <span data-ttu-id="39e71-119">Para más información, consulte [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="39e71-119">For more information, see [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span></span>  
  
4.  <span data-ttu-id="39e71-120">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="39e71-120">When finished, click **Close**.</span></span>  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="39e71-121">le recomienda ver el registro de auditoría mediante el Visor del archivo de registros.</span><span class="sxs-lookup"><span data-stu-id="39e71-121">recommends viewing the audit log by using the Log File Viewer.</span></span> <span data-ttu-id="39e71-122">Pero, si está creando un sistema de supervisión automatizado, puede leer la información en el archivo de auditoría directamente si usa la función [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="39e71-122">However, if you are creating an automated monitoring system, the information in the audit file can be read directly by using the [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql) function.</span></span> <span data-ttu-id="39e71-123">Si lee el archivo directamente, los datos tendrán un formato ligeramente diferente (sin procesar).</span><span class="sxs-lookup"><span data-stu-id="39e71-123">Reading the file directly returns data in a slightly different (unprocessed) format.</span></span> <span data-ttu-id="39e71-124">Vea **Sys. fn_get_audit_file** para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="39e71-124">See **sys.fn_get_audit_file** for more information</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e71-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39e71-125">See Also</span></span>  
 <span data-ttu-id="39e71-126">[SQL Server Audit &#40;motor de base de datos&#41;](sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="39e71-126">[SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="39e71-127">Escribir eventos de SQL Server Audit en el registro de seguridad</span><span class="sxs-lookup"><span data-stu-id="39e71-127">Write SQL Server Audit Events to the Security Log</span></span>](write-sql-server-audit-events-to-the-security-log.md)  
  
  
