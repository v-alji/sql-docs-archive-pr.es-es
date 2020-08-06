---
title: Administrar Oracle CDC Service | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- createSrv
ms.assetid: 5972cee3-b1a9-4c56-aed6-bdddf84af283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f5fbe769980297a06b7958ecad04bfed85b9b714
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744254"
---
# <a name="manage-an-oracle-cdc-service"></a><span data-ttu-id="8954c-102">Manage an Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="8954c-102">Manage an Oracle CDC Service</span></span>
  <span data-ttu-id="8954c-103">Puede usar la Consola de configuración del servicio CDC para administrar un servicio CDC específico.</span><span class="sxs-lookup"><span data-stu-id="8954c-103">You can use the CDC Service Configuration Console to manage a specific CDC Service.</span></span>  
  
 <span data-ttu-id="8954c-104">**Para seleccionar el servicio CDC con el que desea trabajar**</span><span class="sxs-lookup"><span data-stu-id="8954c-104">**To select the CDC service you want to work with**</span></span>  
  
1.  <span data-ttu-id="8954c-105">En el panel izquierdo de la Consola de configuración del servicio CDC, expanda **Servicios CDC locales**.</span><span class="sxs-lookup"><span data-stu-id="8954c-105">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
2.  <span data-ttu-id="8954c-106">Seleccione el servicio CDC con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="8954c-106">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="8954c-107">También puede hacer clic con el botón secundario en el servicio CDC con el que desea trabajar y seleccionar la acción deseada.</span><span class="sxs-lookup"><span data-stu-id="8954c-107">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="8954c-108">Consulte [Lo que puede hacer con un servicio CDC](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="8954c-108">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
 <span data-ttu-id="8954c-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="8954c-109">**OR**</span></span>  
  
1.  <span data-ttu-id="8954c-110">Seleccione **Servicios CDC locales** en el panel izquierdo de la Consola de configuración del servicio CDC.</span><span class="sxs-lookup"><span data-stu-id="8954c-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console.</span></span>  
  
2.  <span data-ttu-id="8954c-111">En la sección central de la Consola de configuración del servicio CDC, seleccione el servicio con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="8954c-111">From the middle section of the CDC Service Configuration Console, select the service you want to work with.</span></span>  
  
     <span data-ttu-id="8954c-112">También puede hacer clic con el botón secundario en el servicio CDC con el que desea trabajar y seleccionar la acción deseada.</span><span class="sxs-lookup"><span data-stu-id="8954c-112">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="8954c-113">Consulte [Lo que puede hacer con un servicio CDC](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="8954c-113">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
##  <a name="what-can-you-do-with-a-cdc-service"></a><a name="BKMK_WhatcandowithCDCService"></a> <span data-ttu-id="8954c-114">Lo que puede hacer con un servicio CDC</span><span class="sxs-lookup"><span data-stu-id="8954c-114">What can you do with a CDC Service</span></span>  
 <span data-ttu-id="8954c-115">Puede realizar las acciones siguientes al trabajar con un servicio CDC.</span><span class="sxs-lookup"><span data-stu-id="8954c-115">You can carry out the following actions when working with a CDC service.</span></span>  
  
### <a name="delete-the-service"></a><span data-ttu-id="8954c-116">Eliminación del servicio</span><span class="sxs-lookup"><span data-stu-id="8954c-116">Delete the service</span></span>  
 <span data-ttu-id="8954c-117">En el panel **Acciones** del lado derecho de la Consola de configuración del servicio CDC, haga clic en **Eliminar** para eliminar el servicio.</span><span class="sxs-lookup"><span data-stu-id="8954c-117">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
 <span data-ttu-id="8954c-118">También puede hacer clic con el botón derecho en el servicio CDC que quiera eliminar y seleccionar **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="8954c-118">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
 <span data-ttu-id="8954c-119">**Nota**: si el servicio se está ejecutando cuando se elimina el servicio, se detendrá el servicio antes de eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="8954c-119">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
 <span data-ttu-id="8954c-120">Para eliminar la definición del servicio de Windows CDC de Oracle, el programa necesita acceso de actualización a la base de datos MSXDBCDC en la instancia asociada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8954c-120">To delete the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="8954c-121">Al hacer clic en Aceptar para eliminar el servicio, el programa intenta eliminar el registro del servicio CDC de Oracle en la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="8954c-121">When you click OK to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="8954c-122">Si el programa no puede eliminar el registro del servicio CDC de Oracle porque no tiene los permisos adecuados, pedirá al usuario que especifique un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con permisos de actualización para la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="8954c-122">If the program cannot delete the Oracle CDC Service registration because it does not have the proper permissions, it prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with update permissions to the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="8954c-123">Para obtener información acerca de los datos que debe especificar en el cuadro de diálogo Conectar con SQL Server, vea [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="8954c-123">For information about the data you must enter in the Connect to SQL Server dialog box, see [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
### <a name="edit-the-cdc-service-properties"></a><span data-ttu-id="8954c-124">Editar las propiedades del servicio CDC</span><span class="sxs-lookup"><span data-stu-id="8954c-124">Edit the CDC Service Properties</span></span>  
 <span data-ttu-id="8954c-125">En el panel **Acciones** del lado derecho de la Consola de configuración del servicio CDC, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8954c-125">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
 <span data-ttu-id="8954c-126">También puede hacer clic con el botón derecho en el servicio CDC cuyas propiedades quiera editar y seleccionar **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8954c-126">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8954c-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8954c-127">See Also</span></span>  
 [<span data-ttu-id="8954c-128">Cómo administrar un servicio CDC local</span><span class="sxs-lookup"><span data-stu-id="8954c-128">How to Manage a Local CDC Service</span></span>](how-to-manage-a-local-cdc-service.md)  
