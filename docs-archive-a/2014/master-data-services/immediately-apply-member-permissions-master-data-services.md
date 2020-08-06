---
title: Aplicar inmediatamente los permisos de los miembros (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- members [Master Data Services], applying permissions immediately
- permissions [Master Data Services], applying member permissions immediately
ms.assetid: 5b16de66-5c39-49f5-992f-402a9eb319aa
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e960ad06213b7c5057a6249b72ce225a6abe35e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674169"
---
# <a name="immediately-apply-member-permissions-master-data-services"></a><span data-ttu-id="c87a1-102">Aplicar inmediatamente los permisos de los miembros (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c87a1-102">Immediately Apply Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="c87a1-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], en lugar de esperar a que la seguridad de los miembros se aplique a intervalos normales, puede aplicar los permisos de miembro inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c87a1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], instead of waiting for member security to be applied at regular intervals, you can apply member permissions immediately.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c87a1-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c87a1-104">Prerequisites</span></span>  
 <span data-ttu-id="c87a1-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="c87a1-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c87a1-106">Debe tener permiso para ejecutar el procedimiento almacenado mds.udpSecurityMemberProcessRebuildModel en la base de datos [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c87a1-106">You must have permission to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="c87a1-107">Para obtener más información, consulte [Seguridad de objetos de base de datos &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c87a1-107">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-immediately-apply-hierarchy-member-permissions"></a><span data-ttu-id="c87a1-108">Para aplicar inmediatamente permisos de miembro de jerarquía</span><span class="sxs-lookup"><span data-stu-id="c87a1-108">To immediately apply hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="c87a1-109">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] y conéctese a la instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)] para la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c87a1-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="c87a1-110">Cree una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="c87a1-110">Create a new query.</span></span>  
  
3.  <span data-ttu-id="c87a1-111">Escriba el siguiente texto y reemplace *database* con el nombre de su base de datos y *Model_Name* con el nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="c87a1-111">Type the following text, replacing *database* with the name of your database and *Model_Name* with the name of the model.</span></span>  
  
    ```  
    USE [database];  
    GO  
  
    DECLARE @Model_ID INT;  
    SELECT @Model_ID = ID FROM mdm.tblModel WHERE [Name] = N'Model_Name';  
    EXEC [mdm].[udpSecurityMemberProcessRebuildModel] @Model_ID=@Model_ID, @ProcessNow=1;  
    GO  
    ```  
  
4.  <span data-ttu-id="c87a1-112">Ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="c87a1-112">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c87a1-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c87a1-113">See Also</span></span>  
 <span data-ttu-id="c87a1-114">[Asignar permisos de miembro de jerarquía &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c87a1-114">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="c87a1-115">Permisos de miembros de la jerarquía &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c87a1-115">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
