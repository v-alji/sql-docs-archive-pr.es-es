---
title: Eliminar una versión (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], deleting
- deleting versions [Master Data Services]
ms.assetid: 2a4eeffe-8379-4744-ad44-c27d8c8ac9a8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f83a3bc396b2a13ac7ac03ef653b16a0d556189a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677182"
---
# <a name="delete-a-version-master-data-services"></a><span data-ttu-id="793a9-102">Eliminar una versión (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="793a9-102">Delete a Version (Master Data Services)</span></span>
  <span data-ttu-id="793a9-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], elimine una versión cuando esté seguro de que ya no necesita los datos maestros asociados a la misma.</span><span class="sxs-lookup"><span data-stu-id="793a9-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a version when you are sure you no longer need the master data associated with the version.</span></span> <span data-ttu-id="793a9-104">Después de eliminar una versión, no puede recuperar los datos maestros asociados.</span><span class="sxs-lookup"><span data-stu-id="793a9-104">After you delete a version, you cannot retrieve the associated master data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="793a9-105">Si un modelo tiene solo una versión y lo elimina, el modelo se vuelve inutilizable.</span><span class="sxs-lookup"><span data-stu-id="793a9-105">If a model has only one version and you delete it, the model becomes unusable.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="793a9-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="793a9-106">Prerequisites</span></span>  
 <span data-ttu-id="793a9-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="793a9-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="793a9-108">Debe tener el permiso para ver la vista mdm.viw_SYSTEM_SCHEMA_VERSION y para ejecutar el procedimiento almacenado mds.udpVersionDelete en la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="793a9-108">You must have permission to view the mdm.viw_SYSTEM_SCHEMA_VERSION view and to execute the mds.udpVersionDelete stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="793a9-109">Para obtener más información, consulte [Seguridad de objetos de base de datos &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="793a9-109">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-version"></a><span data-ttu-id="793a9-110">Para eliminar una versión</span><span class="sxs-lookup"><span data-stu-id="793a9-110">To delete a version</span></span>  
  
1.  <span data-ttu-id="793a9-111">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] y conéctese a la instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)] para la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="793a9-111">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="793a9-112">Abra la vista mdm.viw_SYSTEM_SCHEMA_VERSION.</span><span class="sxs-lookup"><span data-stu-id="793a9-112">Open the mdm.viw_SYSTEM_SCHEMA_VERSION view.</span></span>  
  
3.  <span data-ttu-id="793a9-113">Busque la versión del modelo que desea eliminar y copie el valor en el campo **ID** .</span><span class="sxs-lookup"><span data-stu-id="793a9-113">Find the version of the model you want to delete and copy the value in the **ID** field.</span></span>  
  
4.  <span data-ttu-id="793a9-114">Cree una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="793a9-114">Create a new query.</span></span>  
  
5.  <span data-ttu-id="793a9-115">Escriba el siguiente texto y reemplace *version_ID* con el valor que ha copiado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="793a9-115">Type the following text, replacing *version_ID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpVersionDelete] @Version_ID='version_ID'  
    ```  
  
6.  <span data-ttu-id="793a9-116">Ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="793a9-116">Run the query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="793a9-117">Puede que tenga que esperar unos minutos antes de que la aplicación web refleje el cambio.</span><span class="sxs-lookup"><span data-stu-id="793a9-117">You may have to wait a few minutes before the Web application reflects the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="793a9-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="793a9-118">See Also</span></span>  
 <span data-ttu-id="793a9-119">[Versiones &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="793a9-119">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="793a9-120">Copiar una versión &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="793a9-120">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
  
