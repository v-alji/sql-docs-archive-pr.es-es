---
title: 'La conexión de datos utiliza la autenticación de Windows y las credenciales del usuario no se pudieron delegar. No se pudieron actualizar las siguientes conexiones: datos PowerPivot | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d2006df1-d244-4786-b272-49d8996cc88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: be4c61ad4514f3aa4f6f1eda1fe44ad97c4c064f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671243"
---
# <a name="the-data-connection-uses-windows-authentication-and-user-credentials-could-not-be-delegated-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="c6bf9-103">La conexión de datos utiliza la autenticación de Windows y las credenciales del usuario no se pudieron delegar.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-103">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="c6bf9-104">No se pudieron actualizar las siguientes conexiones: datos PowerPivot</span><span class="sxs-lookup"><span data-stu-id="c6bf9-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="c6bf9-105">En los libros de Excel que contienen datos PowerPivot, Excel Services devuelve este error si no puede conectarse a una instancia del servidor PowerPivot en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to a PowerPivot server instance in SharePoint.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c6bf9-106">Detalles</span><span class="sxs-lookup"><span data-stu-id="c6bf9-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c6bf9-107">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="c6bf9-107">Applies to</span></span>|<span data-ttu-id="c6bf9-108">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="c6bf9-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="c6bf9-109">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c6bf9-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="c6bf9-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6bf9-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="c6bf9-111">Causa</span><span class="sxs-lookup"><span data-stu-id="c6bf9-111">Cause</span></span>|<span data-ttu-id="c6bf9-112">Error en la conexión al intentar utilizar un proveedor de datos PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-112">Connection failed when attempting to use a PowerPivot data provider.</span></span>|  
|<span data-ttu-id="c6bf9-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c6bf9-113">Message Text</span></span>|<span data-ttu-id="c6bf9-114">La conexión de datos utiliza la autenticación de Windows y las credenciales del usuario no se pudieron delegar.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-114">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="c6bf9-115">No se pudieron actualizar las siguientes conexiones: datos PowerPivot</span><span class="sxs-lookup"><span data-stu-id="c6bf9-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c6bf9-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="c6bf9-116">Explanation</span></span>  
 <span data-ttu-id="c6bf9-117">Este mensaje de error tiene varias causas posibles.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-117">There are multiple causes for this error message.</span></span> <span data-ttu-id="c6bf9-118">El factor común de todas ellas es que Servicios de Excel no puede recibir una identidad de usuario de Windows válida de un token de notificaciones en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-118">The common factor behind all of them is that Excel Services cannot get a valid Windows user identity from a claims token in SharePoint.</span></span> <span data-ttu-id="c6bf9-119">En el caso de los libros de Excel que contienen datos PowerPivot, este error se produce cuando se da alguna de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6bf9-119">In the case of Excel workbooks that contain PowerPivot data, this error occurs when any of the following conditions exist:</span></span>  
  
-   <span data-ttu-id="c6bf9-120">Notificaciones del servicio de token de Windows no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-120">The Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="c6bf9-121">Puede confirmar la causa de este error en el archivo de registro de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-121">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="c6bf9-122">Si los registros de SharePoint incluyen el mensaje "El extremo de la canalización 'net.pipe://localhost/s 4u/022694f3-9fbd-422b-b4b2-312e25dae2a2' no se pudo encontrar en el equipo local", Notificaciones del servicio de token de Windows no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-122">If the SharePoint logs include the message "The pipe endpoint 'net.pipe://localhost/s4u/022694f3-9fbd-422b-b4b2-312e25dae2a2' could not be found on your local machine", the Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="c6bf9-123">Para iniciarlo, utilice Administración central y, a continuación, compruebe que el servicio se está ejecutando en la aplicación de consola de Servicios.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-123">To start it, use Central Administration and then verify the service is running in the Services console application.</span></span>  
  
-   <span data-ttu-id="c6bf9-124">Un controlador de dominio no está disponible para validar la identidad del usuario.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-124">A domain controller is not available to validate the user identity.</span></span> <span data-ttu-id="c6bf9-125">Notificaciones del servicio de token de Windows no utiliza las credenciales almacenadas en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-125">The Claims to Windows Token Service does not use cached credentials.</span></span> <span data-ttu-id="c6bf9-126">Valida la identidad del usuario para cada conexión.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-126">It validates the user identity for each connection.</span></span> <span data-ttu-id="c6bf9-127">Puede confirmar la causa de este error en el archivo de registro de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-127">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="c6bf9-128">Si los registros de SharePoint incluyen el mensaje "No se puede obtener WindowsIdentity de IClaimsIdentity", la identidad del usuario no se pudo autenticar.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-128">If the SharePoint logs include the message "Failed to get WindowsIdentity from IClaimsIdentity", the user identity could not be authenticated.</span></span>  
  
-   <span data-ttu-id="c6bf9-129">Los equipos deben ser miembros del mismo dominio o de dominios que tengan una relación de confianza bidireccional.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-129">The computers must be members of the same domain or in domains that have a two-way trust relationship.</span></span>  
  
-   <span data-ttu-id="c6bf9-130">Debe usar cuentas de usuario de dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-130">You must use Windows domain user accounts.</span></span> <span data-ttu-id="c6bf9-131">Las cuentas deben tener un nombre de entidad de seguridad universal (UPN).</span><span class="sxs-lookup"><span data-stu-id="c6bf9-131">The accounts must have a Universal Principal Name (UPN).</span></span>  
  
-   <span data-ttu-id="c6bf9-132">La cuenta de servicio de Servicios de Excel debe tener los permisos de Active Directory para consultar el objeto.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-132">The Excel Services service account must have Active Directory permissions to query the object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c6bf9-133">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c6bf9-133">User Action</span></span>  
 <span data-ttu-id="c6bf9-134">Utilice las siguientes instrucciones para comprobar el estado de Notificaciones del servicio de token de Windows.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-134">Use the following instructions to check the status of the Claims to Windows Token Service.</span></span>  
  
 <span data-ttu-id="c6bf9-135">Para todos los demás escenarios, consulte al administrador de red.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-135">For all other scenarios, check with your network administrator.</span></span>  
  
#### <a name="enable-claims-to-windows-token-service"></a><span data-ttu-id="c6bf9-136">Habilitar Notificaciones del servicio de token de Windows</span><span class="sxs-lookup"><span data-stu-id="c6bf9-136">Enable Claims to Windows Token Service</span></span>  
  
1.  <span data-ttu-id="c6bf9-137">En administración central, en configuración del sistema, haga clic en **administrar servicios en el servidor**.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-137">In Central Administration, in System Settings, click **Manage services on server**.</span></span>  
  
2.  <span data-ttu-id="c6bf9-138">Seleccione **Notificaciones del servicio de token de Windows**y, a continuación, haga clic en **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-138">Select **Claims to Windows Token Service**, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="c6bf9-139">Compruebe que el servicio esté ejecutándose también en la consola Servicios:</span><span class="sxs-lookup"><span data-stu-id="c6bf9-139">Verify the service is also running in the Services console:</span></span>  
  
    1.  <span data-ttu-id="c6bf9-140">En Herramientas administrativas, haga clic en Servicios.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-140">In Administrative Tools, click Services.</span></span>  
  
    2.  <span data-ttu-id="c6bf9-141">Inicie Notificaciones del servicio de token de Windows, si no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c6bf9-141">Start the Claims to Windows Token Service if it is not running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6bf9-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6bf9-142">See Also</span></span>  
 [<span data-ttu-id="c6bf9-143">Configurar las cuentas de servicio PowerPivot</span><span class="sxs-lookup"><span data-stu-id="c6bf9-143">Configure PowerPivot Service Accounts</span></span>](configure-power-pivot-service-accounts.md)  
  
  
