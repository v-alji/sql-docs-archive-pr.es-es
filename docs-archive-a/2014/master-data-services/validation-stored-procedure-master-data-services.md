---
title: Procedimiento almacenado de validación (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 332d3c86-4440-4f12-a6cb-ffbfbccde52c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8fa6b01d950c87768d10b0252c1ccbab2b932fe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673060"
---
# <a name="validation-stored-procedure-master-data-services"></a><span data-ttu-id="e9ab8-102">Procedimiento almacenado de validación (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e9ab8-102">Validation Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="e9ab8-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], valide una versión para aplicar las reglas de negocios a todos los miembros de la versión del modelo.</span><span class="sxs-lookup"><span data-stu-id="e9ab8-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="e9ab8-104">En este tema se explica cómo usar el procedimiento almacenado **mdm.udpValidateModel** para validar datos.</span><span class="sxs-lookup"><span data-stu-id="e9ab8-104">This topic explains how to use the **mdm.udpValidateModel** stored procedure to validate data.</span></span> <span data-ttu-id="e9ab8-105">Si es administrador de la aplicación web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , puede realizar la validación en la interfaz de usuario en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e9ab8-105">If you are an administrator in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you can do validation in the UI instead.</span></span> <span data-ttu-id="e9ab8-106">Para obtener más información, consulte [Validar una versión con las reglas de negocios &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e9ab8-106">For more information, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9ab8-107">Si invoca la validación antes de que se complete el proceso de almacenamiento provisional, no se validarán los miembros que no se hayan terminado de almacenar.</span><span class="sxs-lookup"><span data-stu-id="e9ab8-107">If you invoke validation before the staging process is complete, members that have not finished staging will not be validated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9ab8-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9ab8-108">Example</span></span>  
  
```  
DECLARE @ModelName nVarchar(50) = 'Customer'   
DECLARE @Model_id int   
DECLARE @UserName nvarchar(50)= 'DOMAIN\user_name'   
DECLARE @User_ID int   
DECLARE @Version_ID int   
  
SET @User_ID = (SELECT ID    
                 FROM mdm.tblUser u   
                 WHERE u.UserName = @UserName)   
SET @Model_ID = (SELECT Top 1 Model_ID   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_Name = @ModelName)   
SET @Version_ID = (SELECT MAX(ID)   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_ID = @Model_ID)  
  
EXECUTE mdm.udpValidateModel @User_ID, @Model_ID, @Version_ID, 1  
  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9ab8-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9ab8-109">Parameters</span></span>  
 <span data-ttu-id="e9ab8-110">Los parámetros de este procedimiento son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9ab8-110">The parameters of this procedure are as follows:</span></span>  
  
|<span data-ttu-id="e9ab8-111">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e9ab8-111">Parameter</span></span>|<span data-ttu-id="e9ab8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9ab8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9ab8-113">UserID</span><span class="sxs-lookup"><span data-stu-id="e9ab8-113">UserID</span></span>|<span data-ttu-id="e9ab8-114">Id. de usuario.</span><span class="sxs-lookup"><span data-stu-id="e9ab8-114">The user ID.</span></span>|  
|<span data-ttu-id="e9ab8-115">Model_ID</span><span class="sxs-lookup"><span data-stu-id="e9ab8-115">Model_ID</span></span>|<span data-ttu-id="e9ab8-116">Identificador del modelo.</span><span class="sxs-lookup"><span data-stu-id="e9ab8-116">The model ID.</span></span>|  
|<span data-ttu-id="e9ab8-117">Version_ID</span><span class="sxs-lookup"><span data-stu-id="e9ab8-117">Version_ID</span></span>|<span data-ttu-id="e9ab8-118">Identificador de versión.</span><span class="sxs-lookup"><span data-stu-id="e9ab8-118">The version ID.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9ab8-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9ab8-119">See Also</span></span>  
 <span data-ttu-id="e9ab8-120">[Master Data Services de &#40;de importación de datos&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e9ab8-120">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="e9ab8-121">Validar una versión con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e9ab8-121">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](validate-a-version-against-business-rules-master-data-services.md)  
  
  
