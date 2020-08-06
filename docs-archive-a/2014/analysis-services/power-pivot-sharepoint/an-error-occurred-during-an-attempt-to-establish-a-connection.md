---
title: 'Error al intentar establecer una conexión con el origen de datos externo. No se pudieron actualizar las siguientes conexiones: datos PowerPivot | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1b951da1-f62d-43d2-b40b-270a4a9ab92c
author: minewiskan
ms.author: owend
ms.openlocfilehash: eb4329440b69d1bdfdbb96fbcc3926fa000d8877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746002"
---
# <a name="an-error-occurred-during-an-attempt-to-establish-a-connection-to-the-external-data-source-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="d9d48-103">Error al intentar establecer una conexión con el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="d9d48-103">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="d9d48-104">No se pudieron actualizar las siguientes conexiones: datos PowerPivot</span><span class="sxs-lookup"><span data-stu-id="d9d48-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="d9d48-105">Este error se produce si consulta los datos PowerPivot en un servidor que no tiene instalado PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d9d48-105">This error occurs if you query PowerPivot data on a server that does not have PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="d9d48-106">También se produce si se detiene el servicio SQL Server Analysis Services (PowerPivot) o si se intenta ver los datos PowerPivot de una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="d9d48-106">It also occurs if the SQL Server Analysis Services (PowerPivot) service is stopped, or if you are attempting to view PowerPivot data from an earlier version.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d9d48-107">Detalles</span><span class="sxs-lookup"><span data-stu-id="d9d48-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9d48-108">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="d9d48-108">Applies to</span></span>|<span data-ttu-id="d9d48-109">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="d9d48-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="d9d48-110">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d9d48-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="d9d48-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9d48-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="d9d48-112">Causa</span><span class="sxs-lookup"><span data-stu-id="d9d48-112">Cause</span></span>|<span data-ttu-id="d9d48-113">Error en la conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="d9d48-113">The data connection failed.</span></span>|  
|<span data-ttu-id="d9d48-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d9d48-114">Message Text</span></span>|<span data-ttu-id="d9d48-115">Error al intentar establecer una conexión con el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="d9d48-115">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="d9d48-116">No se pudieron actualizar las siguientes conexiones: datos PowerPivot</span><span class="sxs-lookup"><span data-stu-id="d9d48-116">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d9d48-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="d9d48-117">Explanation</span></span>  
 <span data-ttu-id="d9d48-118">Excel Services devuelve este error al consultar los datos PowerPivot en un libro de Excel que está publicado en SharePoint si el entorno de SharePoint no tiene un servidor PowerPivot para SharePoint o si se detiene la instancia del servicio SQL Server Analysis Services (PowerPivot).</span><span class="sxs-lookup"><span data-stu-id="d9d48-118">Excel Services returns this error when you query PowerPivot data in an Excel workbook that is published to SharePoint, and the SharePoint environment does not have a PowerPivot for SharePoint server, or the SQL Server Analysis Services (PowerPivot) service is stopped.</span></span>  
  
 <span data-ttu-id="d9d48-119">El error se produce al dividir o filtrar los datos PowerPivot cuando el motor de consulta no está disponible.</span><span class="sxs-lookup"><span data-stu-id="d9d48-119">The error occurs when you slice or filter PowerPivot data when the query engine is not available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d9d48-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d9d48-120">User Action</span></span>  
 <span data-ttu-id="d9d48-121">Instale PowerPivot para SharePoint o mueva el libro PowerPivot a un entorno de SharePoint que tenga instalado PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d9d48-121">Install PowerPivot for SharePoint or move the PowerPivot workbook to a SharePoint environment that has PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="d9d48-122">Para obtener más información, vea [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span><span class="sxs-lookup"><span data-stu-id="d9d48-122">For more information, see [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span></span>  
  
 <span data-ttu-id="d9d48-123">Si el software está instalado, compruebe que la instancia de SQL Server Analysis Services (PowerPivot) se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="d9d48-123">If the software is installed, verify that the SQL Server Analysis Services (PowerPivot) instance is running.</span></span> <span data-ttu-id="d9d48-124">Active **Administrar servicios en el servidor** en Administración Central.</span><span class="sxs-lookup"><span data-stu-id="d9d48-124">Check **Manage services on server** in Central Administration.</span></span> <span data-ttu-id="d9d48-125">Seleccione también la aplicación de consola Servicios en Herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="d9d48-125">Also check the Services console application in Administrative Tools.</span></span>  
  
 <span data-ttu-id="d9d48-126">Para los libros PowerPivot que se crearon en una versión SQL Server 2008 R2 de PowerPivot para Excel, se debe instalar la versión SQL Server 2008 R2 del proveedor OLE DB de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d9d48-126">For PowerPivot workbooks that were created in a SQL Server 2008 R2 version of PowerPivot for Excel, you must install the SQL Server 2008 R2 version of the Analysis Services OLE DB provider.</span></span> <span data-ttu-id="d9d48-127">Este error se producirá si ha instalado el proveedor, pero no registró el archivo Microsoft.AnalysisServices.ChannelTransport.dll.</span><span class="sxs-lookup"><span data-stu-id="d9d48-127">This error will occur if you installed the provider, but did not register the Microsoft.AnalysisServices.ChannelTransport.dll file.</span></span> <span data-ttu-id="d9d48-128">Para más información sobre el registro de archivo, consulte [Instalar el proveedor OLE DB de Analysis Services en servidores de SharePoint](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="d9d48-128">For more information about file registration, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9d48-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9d48-129">See Also</span></span>  
 [<span data-ttu-id="d9d48-130">La conexión de datos utiliza la autenticación de Windows y las credenciales de usuario no se pudieron delegar. No se pudieron actualizar las siguientes conexiones: datos PowerPivot</span><span class="sxs-lookup"><span data-stu-id="d9d48-130">The data connection uses Windows Authentication and user credentials could not be delegated. The following connections failed to refresh: PowerPivot Data</span></span>](the-data-connection-user-could-not-be-delegated.md)  
  
  
