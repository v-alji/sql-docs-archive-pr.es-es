---
title: Procedimiento almacenado de almacenamiento provisional (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6a613106-9f87-4caf-a23a-a726fc6561c5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9259352350a099db5d9b18411ad4da06dfb19819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677740"
---
# <a name="staging-stored-procedure-master-data-services"></a><span data-ttu-id="3d250-102">Procedimiento almacenado de almacenamiento provisional (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3d250-102">Staging Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="3d250-103">Al iniciar el proceso de almacenamiento provisional desde [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], use uno de tres procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="3d250-103">When initiating the staging process from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you use one of three stored procedures.</span></span>  
  
-   <span data-ttu-id="3d250-104">stg.udp_name_Leaf</span><span class="sxs-lookup"><span data-stu-id="3d250-104">stg.udp_name_Leaf</span></span>  
  
-   <span data-ttu-id="3d250-105">stg.udp_name_Consolidated</span><span class="sxs-lookup"><span data-stu-id="3d250-105">stg.udp_name_Consolidated</span></span>  
  
-   <span data-ttu-id="3d250-106">stg.udp_name_Relationship</span><span class="sxs-lookup"><span data-stu-id="3d250-106">stg.udp_name_Relationship</span></span>  
  
 <span data-ttu-id="3d250-107">Donde name es el nombre de la tabla de ensayo que se especificó cuando se creó la entidad.</span><span class="sxs-lookup"><span data-stu-id="3d250-107">Where name is the name of the staging table that was specified when the entity was created.</span></span>  
  
## <a name="staging-process-stored-procedure-parameters"></a><span data-ttu-id="3d250-108">Parámetros de los procedimientos almacenados del proceso de almacenamiento provisional</span><span class="sxs-lookup"><span data-stu-id="3d250-108">Staging Process Stored Procedure Parameters</span></span>  
 <span data-ttu-id="3d250-109">En la tabla siguiente se enumeran los parámetros de estos procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="3d250-109">The following table lists the parameters of these stored procedures.</span></span>  
  
|<span data-ttu-id="3d250-110">Parámetro</span><span class="sxs-lookup"><span data-stu-id="3d250-110">Parameter</span></span>|<span data-ttu-id="3d250-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d250-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d250-112">**VersionName**</span><span class="sxs-lookup"><span data-stu-id="3d250-112">**VersionName**</span></span><br /><br /> <span data-ttu-id="3d250-113">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="3d250-113">Required</span></span>|<span data-ttu-id="3d250-114">El nombre de la versión.</span><span class="sxs-lookup"><span data-stu-id="3d250-114">The name of the version.</span></span> <span data-ttu-id="3d250-115">Puede distinguir mayúsculas de minúsculas o no, según la configuración de intercalación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d250-115">This may or may not be case-sensitive, depending on your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] collation setting.</span></span>|  
|<span data-ttu-id="3d250-116">**LogFlag**</span><span class="sxs-lookup"><span data-stu-id="3d250-116">**LogFlag**</span></span><br /><br /> <span data-ttu-id="3d250-117">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="3d250-117">Required</span></span>|<span data-ttu-id="3d250-118">Determina si se registran o no las transacciones durante el proceso de almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="3d250-118">Determines whether transactions are logged during the staging process.</span></span> <span data-ttu-id="3d250-119">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3d250-119">Possible values are:</span></span><br /><br /> <span data-ttu-id="3d250-120">**0**: no registrar transacciones.</span><span class="sxs-lookup"><span data-stu-id="3d250-120">**0**: Do not log transactions.</span></span><br /><span data-ttu-id="3d250-121">**1**: registrar transacciones.</span><span class="sxs-lookup"><span data-stu-id="3d250-121">**1**: Log transactions.</span></span><br /><br /> <br /><br /> <span data-ttu-id="3d250-122">Para obtener más información sobre las transacciones, consulte [Transacciones &#40;Master Data Services&#41;](transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3d250-122">For more information about transactions, see [Transactions &#40;Master Data Services&#41;](transactions-master-data-services.md).</span></span>|  
|<span data-ttu-id="3d250-123">**BatchTag**</span><span class="sxs-lookup"><span data-stu-id="3d250-123">**BatchTag**</span></span><br /><br /> <span data-ttu-id="3d250-124">Obligatorio, excepto para el servicio web</span><span class="sxs-lookup"><span data-stu-id="3d250-124">Required, except by web service</span></span>|<span data-ttu-id="3d250-125">El valor de **BatchTag** como se especifica en la tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="3d250-125">The **BatchTag** value as specified in the staging table.</span></span>|  
|<span data-ttu-id="3d250-126">**Batch_ID**</span><span class="sxs-lookup"><span data-stu-id="3d250-126">**Batch_ID**</span></span><br /><br /> <span data-ttu-id="3d250-127">Solo lo necesita el servicio web</span><span class="sxs-lookup"><span data-stu-id="3d250-127">Required by web service only</span></span>|<span data-ttu-id="3d250-128">El valor de **Batch_ID** como se especifica en la tabla de almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="3d250-128">The **Batch_ID** value as specified in the staging table.</span></span>|  
  
### <a name="staging-process-stored-procedure-example"></a><span data-ttu-id="3d250-129">Ejemplo de procedimiento almacenado del proceso de almacenamiento provisional</span><span class="sxs-lookup"><span data-stu-id="3d250-129">Staging Process Stored Procedure Example</span></span>  
 <span data-ttu-id="3d250-130">En el ejemplo siguiente se muestra cómo iniciar el proceso de almacenamiento provisional mediante el procedimiento almacenado de almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="3d250-130">The following example shows how to start the staging process by using the staging stored procedure.</span></span>  
  
```  
USE [DATABASE_NAME]  
GO  
  
EXEC[stg].[udp_name_Leaf]  
      @VersionName = N'VERSION_1',  
@LogFlag = 1,  
@BatchTag = N'batch1'  
  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d250-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3d250-131">See Also</span></span>  
 <span data-ttu-id="3d250-132">[Master Data Services de &#40;de procedimiento almacenado de validación&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3d250-132">[Validation Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="3d250-133">[Cargar o actualizar miembros en Master Data Services mediante el proceso de almacenamiento provisional](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3d250-133">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 [<span data-ttu-id="3d250-134">Ver los errores que se producen durante el proceso de almacenamiento provisional &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3d250-134">View Errors that Occur During the Staging Process &#40;Master Data Services&#41;</span></span>](view-errors-that-occur-during-staging-master-data-services.md)  
  
  
