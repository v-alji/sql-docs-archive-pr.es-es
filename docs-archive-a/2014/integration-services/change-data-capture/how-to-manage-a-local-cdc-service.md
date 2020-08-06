---
title: Cómo administrar CDC Service local | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f9be649-cd93-40c1-bc48-0480106f207c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 437590d4b91f2fc80d5bb8a90251bf0dc7c8e18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743614"
---
# <a name="how-to-manage-a-local-cdc-service"></a><span data-ttu-id="6e2b7-102">Cómo administrar un servicio CDC local</span><span class="sxs-lookup"><span data-stu-id="6e2b7-102">How to Manage a Local CDC Service</span></span>
  <span data-ttu-id="6e2b7-103">En este procedimiento se describe cómo usar la Consola de configuración del servicio CDC para administrar servicios CDC concretos.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-103">This procedure describes how to use the CDC Service Configuration Console to manage specific CDC services.</span></span>  
  
### <a name="to-manage-a-specific-cdc-service"></a><span data-ttu-id="6e2b7-104">Para administrar un servicio CDC específico</span><span class="sxs-lookup"><span data-stu-id="6e2b7-104">To manage a specific CDC Service</span></span>  
  
1.  <span data-ttu-id="6e2b7-105">En el menú **Inicio** , seleccione **Configuración del servicio CDC para Oracle**.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="6e2b7-106">En el panel izquierdo de la Consola de configuración del servicio CDC, expanda **Servicios CDC locales**.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-106">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
3.  <span data-ttu-id="6e2b7-107">Seleccione el servicio CDC con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-107">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="6e2b7-108">También puede hacer clic con el botón secundario en el servicio CDC con el que desea trabajar y seleccionar la acción deseada.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-108">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
     <span data-ttu-id="6e2b7-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="6e2b7-109">**OR**</span></span>  
  
     <span data-ttu-id="6e2b7-110">Seleccione **Servicios CDC locales** en el panel izquierdo de la Consola de configuración del servicio CDC y, a continuación, seleccione el servicio con el que desea trabajar en la sección central de la consola.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console then select the service you want to work with from the middle section of the CDC Service Configuration Console.</span></span>  
  
     <span data-ttu-id="6e2b7-111">También puede hacer clic con el botón secundario en el servicio CDC con el que desea trabajar y seleccionar la acción deseada.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-111">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
4.  <span data-ttu-id="6e2b7-112">Puede realizar las tareas siguientes al trabajar con un servicio CDC.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-112">You can carry out the following tasks when working with a CDC service.</span></span>  
  
    -   <span data-ttu-id="6e2b7-113">**Eliminar el servicio**</span><span class="sxs-lookup"><span data-stu-id="6e2b7-113">**Delete the service**</span></span>  
  
         <span data-ttu-id="6e2b7-114">En el panel **Acciones** del lado derecho de la Consola de configuración del servicio CDC, haga clic en **Eliminar** para eliminar el servicio.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-114">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
         <span data-ttu-id="6e2b7-115">También puede hacer clic con el botón derecho en el servicio CDC que quiera eliminar y seleccionar **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-115">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
         <span data-ttu-id="6e2b7-116">**Nota**: si el servicio se está ejecutando cuando se elimina el servicio, se detendrá el servicio antes de eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-116">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
         <span data-ttu-id="6e2b7-117">Para eliminar una definición del servicio de Windows CDC de Oracle, el programa necesita acceso de actualización a la base de datos MSXDBCDC en la instancia asociada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e2b7-117">To delete an Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="6e2b7-118">Al hacer clic en **Aceptar** para eliminar el servicio, el programa intenta eliminar el registro del servicio CDC de Oracle en la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-118">When you click **OK** to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="6e2b7-119">Si se produce un error debido a la falta de permisos, aparecerá un cuadro de diálogo que pedirá al usuario que especifique un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con acceso de actualización para la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-119">If it fails due to lack of permissions, a dialog box is displayed to prompt the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
         <span data-ttu-id="6e2b7-120">Para obtener información acerca de los datos que debe especificar en el cuadro de diálogo Conectar con SQL Server, vea [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) y [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="6e2b7-120">For information about the data you must enter in the Connect to SQL Server dialog box, see [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) and [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
    -   <span data-ttu-id="6e2b7-121">**Editar las propiedades del servicio CDC**</span><span class="sxs-lookup"><span data-stu-id="6e2b7-121">**Edit the CDC Service Properties**</span></span>  
  
         <span data-ttu-id="6e2b7-122">En el panel **Acciones** del lado derecho de la Consola de configuración del servicio CDC, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-122">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
         <span data-ttu-id="6e2b7-123">También puede hacer clic con el botón derecho en el servicio CDC cuyas propiedades quiera editar y seleccionar **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6e2b7-123">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e2b7-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e2b7-124">See Also</span></span>  
 [<span data-ttu-id="6e2b7-125">Administrar un servicio CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="6e2b7-125">Manage an Oracle CDC Service</span></span>](manage-an-oracle-cdc-service.md)  
  
  
