---
title: Cambiar la cuenta de administrador del sistema (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], changing
ms.assetid: cf30312e-4338-49a7-90f0-6e4f7b431ff8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d13cdc19c70c9e16c92dfd290393739d7e4f5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747069"
---
# <a name="change-the-system-administrator-account-master-data-services"></a><span data-ttu-id="aea3e-102">Cambiar la cuenta de administrador del sistema (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="aea3e-102">Change the System Administrator Account (Master Data Services)</span></span>
  <span data-ttu-id="aea3e-103">Puede cambiar la cuenta de usuario designada como [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="aea3e-103">You can change the user account that is designated as the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="aea3e-104">Al completar este procedimiento, se elimina la cuenta de usuario del administrador del sistema anterior.</span><span class="sxs-lookup"><span data-stu-id="aea3e-104">When you complete this procedure, the former system administrator user account is deleted.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aea3e-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aea3e-105">Prerequisites</span></span>  
 <span data-ttu-id="aea3e-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="aea3e-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="aea3e-107">Debe agregar el nombre de usuario del nuevo administrador a la lista de usuarios de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aea3e-107">You must add the new administrator's user name to the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Users list.</span></span> <span data-ttu-id="aea3e-108">Para obtener más información, vea [Agregar un usuario &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="aea3e-108">For more information, see [Add a User &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="aea3e-109">Debe tener permiso para ver mdm.tblUser y ejecutar el procedimiento almacenado mdm.udpSecurityMemberProcessRebuildModel en la base de datos [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aea3e-109">You must have permission to view mdm.tblUser and to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="aea3e-110">Para obtener más información, consulte [Seguridad de objetos de base de datos &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="aea3e-110">For more information, see [Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-change-the-administrator-account"></a><span data-ttu-id="aea3e-111">Para cambiar la cuenta del administrador</span><span class="sxs-lookup"><span data-stu-id="aea3e-111">To change the administrator account</span></span>  
  
1.  <span data-ttu-id="aea3e-112">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] y conéctese a la instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)] para la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aea3e-112">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="aea3e-113">En MDM. tblUser, busque el usuario que será el nuevo administrador y copie el valor en la `SID` columna.</span><span class="sxs-lookup"><span data-stu-id="aea3e-113">In mdm.tblUser, find the user that will be the new administrator and copy the value in the `SID` column.</span></span>  
  
3.  <span data-ttu-id="aea3e-114">Cree una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="aea3e-114">Create a new query.</span></span>  
  
4.  <span data-ttu-id="aea3e-115">Escriba el siguiente texto, reemplazando *dominio \ user_name* por el nombre de usuario y el *SID* del nuevo administrador por el valor que copió en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="aea3e-115">Type the following text, replacing *DOMAIN\user_name* with the new administrator's user name and *SID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpSecuritySetAdministrator] @UserName='DOMAIN\user_name', @SID = 'SID', @PromoteNonAdmin = 1  
    ```  
  
5.  <span data-ttu-id="aea3e-116">Ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="aea3e-116">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea3e-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aea3e-117">See Also</span></span>  
 [<span data-ttu-id="aea3e-118">Administradores &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="aea3e-118">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
  
