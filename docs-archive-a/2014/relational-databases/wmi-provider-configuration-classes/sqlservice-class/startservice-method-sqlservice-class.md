---
title: Método StartService (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartService method
ms.assetid: 83dfb6bd-dbd5-45d8-aad2-a11926317f91
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4d91646da2ac2c9f636655ff6c65808ba115e28f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746816"
---
# <a name="startservice-method-sqlservice-class"></a><span data-ttu-id="5b0da-102">Método StartService (clase SqlService)</span><span class="sxs-lookup"><span data-stu-id="5b0da-102">StartService Method (SqlService Class)</span></span>
  <span data-ttu-id="5b0da-103">Intenta poner el servicio en estado iniciado.</span><span class="sxs-lookup"><span data-stu-id="5b0da-103">Attempts to place the service into its started state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b0da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b0da-104">Syntax</span></span>  
  
```  
  
object  
.StartService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="5b0da-105">Partes</span><span class="sxs-lookup"><span data-stu-id="5b0da-105">Parts</span></span>  
 <span data-ttu-id="5b0da-106">*object*</span><span class="sxs-lookup"><span data-stu-id="5b0da-106">*object*</span></span>  
 <span data-ttu-id="5b0da-107">Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5b0da-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5b0da-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="5b0da-109">Valor uint32 que especifica uno de los estados de inicio siguientes.</span><span class="sxs-lookup"><span data-stu-id="5b0da-109">A uint32 value that specifies one of the following startup states.</span></span>  
  
 <span data-ttu-id="5b0da-110">0</span><span class="sxs-lookup"><span data-stu-id="5b0da-110">0</span></span>  
 <span data-ttu-id="5b0da-111">Correcto.</span><span class="sxs-lookup"><span data-stu-id="5b0da-111">Success.</span></span> <span data-ttu-id="5b0da-112">Se aceptó la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5b0da-112">The request was accepted.</span></span>  
  
 <span data-ttu-id="5b0da-113">1</span><span class="sxs-lookup"><span data-stu-id="5b0da-113">1</span></span>  
 <span data-ttu-id="5b0da-114">No compatible.</span><span class="sxs-lookup"><span data-stu-id="5b0da-114">Not Supported.</span></span> <span data-ttu-id="5b0da-115">No se admite la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5b0da-115">The request is not supported.</span></span>  
  
 <span data-ttu-id="5b0da-116">2</span><span class="sxs-lookup"><span data-stu-id="5b0da-116">2</span></span>  
 <span data-ttu-id="5b0da-117">Acceso denegado.</span><span class="sxs-lookup"><span data-stu-id="5b0da-117">Access Denied.</span></span> <span data-ttu-id="5b0da-118">El usuario no tenía el permiso de acceso adecuado.</span><span class="sxs-lookup"><span data-stu-id="5b0da-118">The user did not have appropriate access.</span></span>  
  
 <span data-ttu-id="5b0da-119">3</span><span class="sxs-lookup"><span data-stu-id="5b0da-119">3</span></span>  
 <span data-ttu-id="5b0da-120">Servicios dependientes en ejecución.</span><span class="sxs-lookup"><span data-stu-id="5b0da-120">Dependent Services Running.</span></span> <span data-ttu-id="5b0da-121">No se puede detener el servicio porque otros servicios que se están ejecutando dependen de él.</span><span class="sxs-lookup"><span data-stu-id="5b0da-121">The service cannot be stopped because other services that are running are dependent on it.</span></span>  
  
 <span data-ttu-id="5b0da-122">4</span><span class="sxs-lookup"><span data-stu-id="5b0da-122">4</span></span>  
 <span data-ttu-id="5b0da-123">Control de servicio no válido.</span><span class="sxs-lookup"><span data-stu-id="5b0da-123">Invalid Service Control.</span></span> <span data-ttu-id="5b0da-124">El código de control solicitado no es válido o no es aceptable para el servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-124">The requested control code is not valid, or it is unacceptable to the service.</span></span>  
  
 <span data-ttu-id="5b0da-125">5</span><span class="sxs-lookup"><span data-stu-id="5b0da-125">5</span></span>  
 <span data-ttu-id="5b0da-126">El servicio no puede aceptar el control.</span><span class="sxs-lookup"><span data-stu-id="5b0da-126">Service Cannot Accept Control.</span></span> <span data-ttu-id="5b0da-127">El código de control solicitado no se puede enviar al servicio porque el estado del servicio (Win32_BaseService:State) es igual a 0, 1 ó 2.</span><span class="sxs-lookup"><span data-stu-id="5b0da-127">The requested control code cannot be sent to the service because the state of the service (Win32_BaseService:State) is equal to 0, 1, or 2.</span></span>  
  
 <span data-ttu-id="5b0da-128">6</span><span class="sxs-lookup"><span data-stu-id="5b0da-128">6</span></span>  
 <span data-ttu-id="5b0da-129">Servicio no activo.</span><span class="sxs-lookup"><span data-stu-id="5b0da-129">Service Not Active.</span></span> <span data-ttu-id="5b0da-130">El servicio no se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="5b0da-130">The service has not been started.</span></span>  
  
 <span data-ttu-id="5b0da-131">7</span><span class="sxs-lookup"><span data-stu-id="5b0da-131">7</span></span>  
 <span data-ttu-id="5b0da-132">Tiempo de espera de solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-132">Service Request Timeout.</span></span> <span data-ttu-id="5b0da-133">El servicio no respondió a tiempo a la solicitud de inicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-133">The service did not respond to the start request in a timely fashion.</span></span>  
  
 <span data-ttu-id="5b0da-134">8</span><span class="sxs-lookup"><span data-stu-id="5b0da-134">8</span></span>  
 <span data-ttu-id="5b0da-135">Error desconocido.</span><span class="sxs-lookup"><span data-stu-id="5b0da-135">Unknown Failure.</span></span> <span data-ttu-id="5b0da-136">Se produjo un error desconocido al iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-136">An unknown failure occurred when starting the service.</span></span>  
  
 <span data-ttu-id="5b0da-137">9</span><span class="sxs-lookup"><span data-stu-id="5b0da-137">9</span></span>  
 <span data-ttu-id="5b0da-138">No se ha encontrado la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="5b0da-138">Path Not Found.</span></span> <span data-ttu-id="5b0da-139">No se encontró la ruta de acceso al directorio del ejecutable del servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-139">The directory path to the service executable was not found.</span></span>  
  
 <span data-ttu-id="5b0da-140">10</span><span class="sxs-lookup"><span data-stu-id="5b0da-140">10</span></span>  
 <span data-ttu-id="5b0da-141">Servicio ya en ejecución.</span><span class="sxs-lookup"><span data-stu-id="5b0da-141">Service Already Running.</span></span> <span data-ttu-id="5b0da-142">El servicio ya se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="5b0da-142">The service is already running.</span></span>  
  
 <span data-ttu-id="5b0da-143">11</span><span class="sxs-lookup"><span data-stu-id="5b0da-143">11</span></span>  
 <span data-ttu-id="5b0da-144">Base de datos de servicio bloqueada.</span><span class="sxs-lookup"><span data-stu-id="5b0da-144">Service Database Locked.</span></span> <span data-ttu-id="5b0da-145">La base de datos para agregar un nuevo servicio está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="5b0da-145">The database to add a new service is locked.</span></span>  
  
 <span data-ttu-id="5b0da-146">12</span><span class="sxs-lookup"><span data-stu-id="5b0da-146">12</span></span>  
 <span data-ttu-id="5b0da-147">Dependencia de servicio eliminada.</span><span class="sxs-lookup"><span data-stu-id="5b0da-147">Service Dependency Deleted.</span></span> <span data-ttu-id="5b0da-148">Una dependencia en la que se basaba este servicio se ha quitado del sistema.</span><span class="sxs-lookup"><span data-stu-id="5b0da-148">A dependency on which this service relies has been removed from the system.</span></span>  
  
 <span data-ttu-id="5b0da-149">13</span><span class="sxs-lookup"><span data-stu-id="5b0da-149">13</span></span>  
 <span data-ttu-id="5b0da-150">Error de dependencia de servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-150">Service Dependency Failure.</span></span> <span data-ttu-id="5b0da-151">El servicio no pudo encontrar el servicio necesario de un servicio dependiente.</span><span class="sxs-lookup"><span data-stu-id="5b0da-151">The service failed to find the service needed from a dependent service.</span></span>  
  
 <span data-ttu-id="5b0da-152">14</span><span class="sxs-lookup"><span data-stu-id="5b0da-152">14</span></span>  
 <span data-ttu-id="5b0da-153">Servicio deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="5b0da-153">Service Disabled.</span></span> <span data-ttu-id="5b0da-154">El servicio se ha deshabilitado del sistema.</span><span class="sxs-lookup"><span data-stu-id="5b0da-154">The service has been disabled from the system.</span></span>  
  
 <span data-ttu-id="5b0da-155">15</span><span class="sxs-lookup"><span data-stu-id="5b0da-155">15</span></span>  
 <span data-ttu-id="5b0da-156">Error de inicio de sesión del servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-156">Service Logon Failed.</span></span> <span data-ttu-id="5b0da-157">El servicio no tiene la autenticación correcta para ejecutarse en el sistema.</span><span class="sxs-lookup"><span data-stu-id="5b0da-157">The service does not have the correct authentication to run on the system.</span></span>  
  
 <span data-ttu-id="5b0da-158">16</span><span class="sxs-lookup"><span data-stu-id="5b0da-158">16</span></span>  
 <span data-ttu-id="5b0da-159">Servicio marcado para eliminación.</span><span class="sxs-lookup"><span data-stu-id="5b0da-159">Service Marked For Deletion.</span></span> <span data-ttu-id="5b0da-160">El servicio se va a quitar del sistema.</span><span class="sxs-lookup"><span data-stu-id="5b0da-160">The service is being removed from the system.</span></span>  
  
 <span data-ttu-id="5b0da-161">17</span><span class="sxs-lookup"><span data-stu-id="5b0da-161">17</span></span>  
 <span data-ttu-id="5b0da-162">Servicio sin subproceso.</span><span class="sxs-lookup"><span data-stu-id="5b0da-162">Service No Thread.</span></span> <span data-ttu-id="5b0da-163">No hay ningún subproceso de ejecución para el servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-163">There is no execution thread for the service.</span></span>  
  
 <span data-ttu-id="5b0da-164">18</span><span class="sxs-lookup"><span data-stu-id="5b0da-164">18</span></span>  
 <span data-ttu-id="5b0da-165">Estado Dependencia circular.</span><span class="sxs-lookup"><span data-stu-id="5b0da-165">Status Circular Dependency.</span></span> <span data-ttu-id="5b0da-166">Hay dependencias circulares al iniciarse el servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-166">There are circular dependencies when starting the service.</span></span>  
  
 <span data-ttu-id="5b0da-167">19</span><span class="sxs-lookup"><span data-stu-id="5b0da-167">19</span></span>  
 <span data-ttu-id="5b0da-168">Estado Nombre replicado.</span><span class="sxs-lookup"><span data-stu-id="5b0da-168">Status Duplicate Name.</span></span> <span data-ttu-id="5b0da-169">Hay un servicio que se ejecuta con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="5b0da-169">There is a service running under the same name.</span></span>  
  
 <span data-ttu-id="5b0da-170">20</span><span class="sxs-lookup"><span data-stu-id="5b0da-170">20</span></span>  
 <span data-ttu-id="5b0da-171">Estado Nombre no válido.</span><span class="sxs-lookup"><span data-stu-id="5b0da-171">Status Invalid Name.</span></span> <span data-ttu-id="5b0da-172">Hay caracteres no válidos en el nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-172">There are characters that are not valid in the name of the service.</span></span>  
  
 <span data-ttu-id="5b0da-173">21</span><span class="sxs-lookup"><span data-stu-id="5b0da-173">21</span></span>  
 <span data-ttu-id="5b0da-174">Estado Parámetro no válido.</span><span class="sxs-lookup"><span data-stu-id="5b0da-174">Status Invalid Parameter.</span></span> <span data-ttu-id="5b0da-175">Se han pasado parámetros no válidos al servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-175">Parameters that are not valid have been passed to the service.</span></span>  
  
 <span data-ttu-id="5b0da-176">22</span><span class="sxs-lookup"><span data-stu-id="5b0da-176">22</span></span>  
 <span data-ttu-id="5b0da-177">Estado Cuenta de servicio no válida.</span><span class="sxs-lookup"><span data-stu-id="5b0da-177">Status Invalid Service Account.</span></span> <span data-ttu-id="5b0da-178">La cuenta bajo la que se ejecuta este servicio no es válida o carece de permisos para ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="5b0da-178">The account which this service is to run under is not valid, or it lacks the permissions to run the service.</span></span>  
  
 <span data-ttu-id="5b0da-179">23</span><span class="sxs-lookup"><span data-stu-id="5b0da-179">23</span></span>  
 <span data-ttu-id="5b0da-180">Estado El servicio existe.</span><span class="sxs-lookup"><span data-stu-id="5b0da-180">Status Service Exists.</span></span> <span data-ttu-id="5b0da-181">El servicio existe en la base de datos de servicios disponibles del sistema.</span><span class="sxs-lookup"><span data-stu-id="5b0da-181">The service exists in the database of services available from the system.</span></span>  
  
 <span data-ttu-id="5b0da-182">24</span><span class="sxs-lookup"><span data-stu-id="5b0da-182">24</span></span>  
 <span data-ttu-id="5b0da-183">Servicio ya pausado.</span><span class="sxs-lookup"><span data-stu-id="5b0da-183">Service Already Paused.</span></span> <span data-ttu-id="5b0da-184">El servicio se encuentra en pausa actualmente en el sistema.</span><span class="sxs-lookup"><span data-stu-id="5b0da-184">The service is currently paused in the system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b0da-185">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5b0da-185">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b0da-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b0da-186">See Also</span></span>  
 <span data-ttu-id="5b0da-187">[Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="5b0da-187">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
