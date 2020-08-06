---
title: Agregar MSOLAP. 5 como proveedor de datos de confianza en Excel Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1f40fa4-de6d-41ee-8124-14b4d65988f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 876ec613f18b2d91b5e06ab5fed4a7b258c30a36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676211"
---
# <a name="add-msolap5-as-a-trusted-data-provider-in-excel-services"></a><span data-ttu-id="80525-102">Agregar MSOLAP.5 como proveedor de datos de confianza en Excel Services</span><span class="sxs-lookup"><span data-stu-id="80525-102">Add MSOLAP.5 as a Trusted Data Provider in Excel Services</span></span>
  <span data-ttu-id="80525-103">MSOLAP.5 hace referencia al proveedor OLE DB de Analysis Services para SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="80525-103">MSOLAP.5 refers to the Analysis Services OLE DB provider for SQL Server 2012.</span></span> <span data-ttu-id="80525-104">Excel Services debe confiar en este proveedor para que pueda realizar la solicitud de conexión que tiene como resultado la disponibilidad de los datos de PowerPivot en un servidor.</span><span class="sxs-lookup"><span data-stu-id="80525-104">Excel Services must trust this provider before it will make the connection request that results in the availability of PowerPivot data on a server.</span></span>  
  
 <span data-ttu-id="80525-105">Si configuró PowerPivot para SharePoint mediante la herramienta de configuración de PowerPivot, MSOLAP.5 ya puede ser proveedor de confianza porque la herramienta incluye una acción que cumple este requisito.</span><span class="sxs-lookup"><span data-stu-id="80525-105">If you configured PowerPivot for SharePoint using the PowerPivot Configuration Tool, MSOLAP.5 might already be a trusted provider because the tool includes an action that satisfies this requirement.</span></span> <span data-ttu-id="80525-106">Sin embargo, si usa PowerShell o, si se excluyó la acción de proveedor de confianza en la herramienta de configuración, es posible que no se encuentre Administración central o el proveedor. En ese caso, debe agregarlos como parte de la configuración de la granja de servidores para el acceso a datos PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="80525-106">However, if you are using PowerShell, Central Administration, or if you excluded the trusted provider action in the configuration tool, the provider might be missing, which case you should add it now as part of configuring the farm for PowerPivot data access.</span></span>  
  
 <span data-ttu-id="80525-107">Solo necesita realizar este paso una vez para cada aplicación de servicios de Excel Services.</span><span class="sxs-lookup"><span data-stu-id="80525-107">You only need to perform this step once for each Excel Services service application.</span></span>  
  
 <span data-ttu-id="80525-108">Cada servidor físico que controla una solicitud de datos PowerPivot, como un servidor PowerPivot para SharePoint o un servidor de Excel Services, debe tener instalado el proveedor OLE DB en el equipo.</span><span class="sxs-lookup"><span data-stu-id="80525-108">Each physical server that handles a PowerPivot data request, such as a PowerPivot for SharePoint server or an Excel Services server, must have the OLE DB provider installed on the computer.</span></span> <span data-ttu-id="80525-109">Una instalación de PowerPivot para SharePoint incluye siempre el proveedor OLE DB, pero si Excel Services se ejecuta en un equipo que no dispone de PowerPivot para SharePoint, debe instalar el proveedor manualmente.</span><span class="sxs-lookup"><span data-stu-id="80525-109">A PowerPivot for SharePoint installation always includes the OLE DB provider, but if Excel Services is running on a computer that does not have PowerPivot for SharePoint, you must install the provider manually.</span></span> <span data-ttu-id="80525-110">Para más información, consulte [Instalar el proveedor OLE DB de Analysis Services en servidores de SharePoint](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="80525-110">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="add-a-trusted-provider-to-excel-services"></a><span data-ttu-id="80525-111">Agregue un proveedor de confianza en Excel Services</span><span class="sxs-lookup"><span data-stu-id="80525-111">Add a trusted provider to Excel Services</span></span>  
  
1.  <span data-ttu-id="80525-112">En Administración central, haga clic en **Administrar aplicaciones de servicio**y haga clic en la aplicación de servicios de Excel Services.</span><span class="sxs-lookup"><span data-stu-id="80525-112">In Central Administration, click **Manage service applications**, and then click the Excel Services service application.</span></span>  
  
2.  <span data-ttu-id="80525-113">Haga clic en **Proveedores de datos de confianza**.</span><span class="sxs-lookup"><span data-stu-id="80525-113">Click **Trusted Data Providers**.</span></span>  
  
3.  <span data-ttu-id="80525-114">Compruebe que MSOLAP.5 aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="80525-114">Verify that MSOLAP.5 appears in the list.</span></span> <span data-ttu-id="80525-115">Según el modo en que configuró PowerPivot para SharePoint, MSOLAP.5 podría ya ser de confianza.</span><span class="sxs-lookup"><span data-stu-id="80525-115">Depending on how you configured PowerPivot for SharePoint, MSOLAP.5 might already be trusted.</span></span>  
  
4.  <span data-ttu-id="80525-116">Si no aparece, haga clic en **Agregar proveedor de datos de confianza**.</span><span class="sxs-lookup"><span data-stu-id="80525-116">If it is not listed, click **Add Trusted Data Provider**.</span></span>  
  
5.  <span data-ttu-id="80525-117">En el identificador del proveedor, escriba `MSOLAP.5`.</span><span class="sxs-lookup"><span data-stu-id="80525-117">In Provider ID, type `MSOLAP.5`.</span></span>  
  
6.  <span data-ttu-id="80525-118">En Tipo de proveedor, asegúrese de que está seleccionado OLE DB.</span><span class="sxs-lookup"><span data-stu-id="80525-118">For Provider Type, ensure that OLE DB is selected.</span></span>  
  
7.  <span data-ttu-id="80525-119">En Descripción del proveedor, escriba **Proveedor OLE DB de Microsoft para OLAP Services 11.0**.</span><span class="sxs-lookup"><span data-stu-id="80525-119">In Provider Description, type **Microsoft OLE DB Provider for OLAP Services 11.0**.</span></span>  
  
  
