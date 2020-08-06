---
title: Instalación de ADOMD.NET en servidores front-end web ejecutando administración central | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2372180-e847-4cdb-b267-4befac3faf7e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 0d9f52bf612c4878a8dacd4f5acfdcc135ae115e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663298"
---
# <a name="install-adomdnet-on-web-front-end-servers-running-central-administration"></a><span data-ttu-id="cbcfd-102">Instalar ADOMD.NET en servidores front-end web ejecutando Administración central</span><span class="sxs-lookup"><span data-stu-id="cbcfd-102">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>
  <span data-ttu-id="cbcfd-103">Si instala PowerPivot para SharePoint en una granja que tiene la topología de Administración central, sin Excel Services o PowerPivot para SharePoint, descargue e instale la biblioteca de cliente de Microsoft ADOMD.NET si desea acceso total a los informes integrados en el panel de administración de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-103">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="cbcfd-104">Algunos informes del panel usan ADOMD.NET para tener acceso a los datos internos que proporcionan los datos de errores en el procesamiento de las consultas de PowerPivot y el estado del servidor en la granja.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-104">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span>  
  
 <span data-ttu-id="cbcfd-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="cbcfd-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010</span></span>  
  
 <span data-ttu-id="cbcfd-106">En SharePoint 2013, el proveedor se incluye en el Feature Pack de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-106">For SharePoint 2013, the provider is included in the SQL Server feature pack.</span></span> <span data-ttu-id="cbcfd-107">Para obtener información sobre cómo descargar spPowerPivot.msi, consulte [Microsoft SQL Server 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=35577)</span><span class="sxs-lookup"><span data-stu-id="cbcfd-107">For information on how to download spPowerPivot.msi, see [Microsoft SQL Server 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=35577)</span></span>  
  
### <a name="download-and-install-the-client-library"></a><span data-ttu-id="cbcfd-108">Descargar e instalar la biblioteca de cliente</span><span class="sxs-lookup"><span data-stu-id="cbcfd-108">Download and install the client library</span></span>  
  
1.  <span data-ttu-id="cbcfd-109">En la [página SQL Server Feature Pack de 2014](https://go.microsoft.com/fwlink/?LinkID=296473), busque Microsoft ADOMD.net.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-109">On the [SQL Server 2014 Feature Pack page](https://go.microsoft.com/fwlink/?LinkID=296473), find Microsoft ADOMD.NET.</span></span>  
  
2.  <span data-ttu-id="cbcfd-110">Descargue el paquete x64 del programa de instalación de `SQL_AS_ADOMD.msi`.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-110">Download the x64 Package of the `SQL_AS_ADOMD.msi` installation program.</span></span>  
  
3.  <span data-ttu-id="cbcfd-111">Ejecute el archivo .msi para instalar la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-111">Run the .msi to install the library.</span></span>  
  
4.  <span data-ttu-id="cbcfd-112">Restaurar IIS una vez finalizada la instalación.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-112">Reset IIS after installation is finished.</span></span> <span data-ttu-id="cbcfd-113">Abra un símbolo del sistema administrativo y escriba **iisreset**.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-113">Open an administrative command prompt and type **IISRESET**.</span></span>  
  
### <a name="verify-installation"></a><span data-ttu-id="cbcfd-114">Comprobar la instalación</span><span class="sxs-lookup"><span data-stu-id="cbcfd-114">Verify installation</span></span>  
  
1.  <span data-ttu-id="cbcfd-115">Vaya a Windows\Assembly.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-115">Go to Windows\Assembly.</span></span>  
  
2.  <span data-ttu-id="cbcfd-116">Haga clic con el botón secundario en Microsoft. AnalysisServices. AdomdClient y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-116">Right-click Microsoft.AnalysisServices.AdomdClient and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="cbcfd-117">Haga clic en **Versión**.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-117">Click **Version**.</span></span>  
  
4.  <span data-ttu-id="cbcfd-118">Compruebe que la versión incluye 12,00.\<build number></span><span class="sxs-lookup"><span data-stu-id="cbcfd-118">Verify that the version includes 12.00.\<build number></span></span> <span data-ttu-id="cbcfd-119">y que la descripción es Microsoft. AnalysisService. AdomdClient.</span><span class="sxs-lookup"><span data-stu-id="cbcfd-119">and that the description is Microsoft.AnalysisService.AdomdClient.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbcfd-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cbcfd-120">See Also</span></span>  
 [<span data-ttu-id="cbcfd-121">Panel de administración de PowerPivot y datos de uso</span><span class="sxs-lookup"><span data-stu-id="cbcfd-121">PowerPivot Management Dashboard and Usage Data</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data)  
  
  
