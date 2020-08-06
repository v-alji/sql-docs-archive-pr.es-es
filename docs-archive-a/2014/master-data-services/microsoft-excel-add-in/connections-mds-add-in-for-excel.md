---
title: Conexiones (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 2f2b2f9d-7744-460e-83cd-56d34ea70ff0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d4dc41afc6dd59cade9e75475c7cb914d14a8937
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662140"
---
# <a name="connections-mds-add-in-for-excel"></a><span data-ttu-id="24108-102">Conexiones (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="24108-102">Connections (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="24108-103">Para descargar datos en [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], primero debe crear una conexión.</span><span class="sxs-lookup"><span data-stu-id="24108-103">To download data in to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must first create a connection.</span></span> <span data-ttu-id="24108-104">Una conexión es la forma en que el servicio web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] sabe a qué base de datos de MDS se debe conectar.</span><span class="sxs-lookup"><span data-stu-id="24108-104">A connection is how the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service knows which MDS database to connect to.</span></span>  
  
 <span data-ttu-id="24108-105">La cadena de conexión suele ser la dirección URL de la aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]; por ejemplo, http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="24108-105">The connection string is usually the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
 <span data-ttu-id="24108-106">Cada vez que inicia Excel, debe conectarse a un repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="24108-106">Each time you start Excel, you must connect to an MDS repository.</span></span> <span data-ttu-id="24108-107">La única excepción es cuando la hoja de cálculo activa ya contiene datos administrados por MDS.</span><span class="sxs-lookup"><span data-stu-id="24108-107">The only exception is when the active spreadsheet already contains MDS-managed data.</span></span> <span data-ttu-id="24108-108">En este caso, la conexión se realiza automáticamente cada vez que se actualizan o publican datos en la hoja.</span><span class="sxs-lookup"><span data-stu-id="24108-108">In this case, a connection is automatically made each time you refresh or publish data in the sheet.</span></span>  
  
 <span data-ttu-id="24108-109">Se pueden crear varias conexiones.</span><span class="sxs-lookup"><span data-stu-id="24108-109">You can create multiple connections.</span></span> <span data-ttu-id="24108-110">La conexión a la que se ha obtenido acceso más recientemente se considera la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="24108-110">The most recently-accessed connection is considered the default.</span></span>  
  
 <span data-ttu-id="24108-111">Pueden conectarse varios usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="24108-111">Multiple users can be connected at the same time.</span></span> <span data-ttu-id="24108-112">Sin embargo, pueden surgir conflictos cuando varios usuarios intentan publicar los mismos datos.</span><span class="sxs-lookup"><span data-stu-id="24108-112">However, conflicts can arise when multiple users attempt to publish the same data.</span></span> <span data-ttu-id="24108-113">Para obtener más información, vea [publicar datos &#40;Complemento MDS para Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="24108-113">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>  
  
## <a name="connect-automatically-and-load-frequently-used-data"></a><span data-ttu-id="24108-114">Conectar automáticamente y cargar datos utilizados con frecuencia</span><span class="sxs-lookup"><span data-stu-id="24108-114">Connect Automatically and Load Frequently-Used Data</span></span>  
 <span data-ttu-id="24108-115">Si desea conectarse al mismo servidor y cargar siempre el mismo conjunto de datos, puede crear archivos de consulta de acceso directo, que contienen la información de conexión y filtro.</span><span class="sxs-lookup"><span data-stu-id="24108-115">If you want to always connect to the same server and load the same set of data, you can create shortcut query files, which contain connection and filter information.</span></span> <span data-ttu-id="24108-116">Para obtener más información sobre los archivos de consulta, consulte [Archivos de consulta de acceso directo &#40;complemento MDS para Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="24108-116">For more information about query files, see [Shortcut Query Files &#40;MDS Add-in for Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span></span>  
  
## <a name="data-quality-services"></a><span data-ttu-id="24108-117">Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="24108-117">Data Quality Services</span></span>  
 <span data-ttu-id="24108-118">[!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] incluye la funcionalidad Data Quality Services para ayudarle a comparar los datos antes de publicarlos en el repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="24108-118">The [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] has Data Quality Services functionality to help you match data before publishing it to the MDS repository.</span></span> <span data-ttu-id="24108-119">Cuando se realiza una conexión, si hay una base de datos de DQS instalada en la misma instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que la base de datos de MDS, podrá ver los botones de DQS en la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="24108-119">When you make a connection, if a DQS database is installed on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the MDS database, you will be able to view DQS buttons on the ribbon.</span></span> <span data-ttu-id="24108-120">Si la base de datos DQS_Main no existe en la instancia, estos botones no se muestran y la funcionalidad de calidad de los datos no está disponible.</span><span class="sxs-lookup"><span data-stu-id="24108-120">If the DQS_Main database does not exist on the instance, these buttons are not displayed and data quality functionality is not available.</span></span>  
  
## <a name="troubleshooting-connections"></a><span data-ttu-id="24108-121">Solucionar problemas de las conexiones</span><span class="sxs-lookup"><span data-stu-id="24108-121">Troubleshooting Connections</span></span>  
 <span data-ttu-id="24108-122">Cuando se conecte a MDS, si encuentra algún problema, consulte [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) para obtener sugerencias para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="24108-122">When you connect to MDS, if you encounter any issues see [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) for troubleshooting tips.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="24108-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="24108-123">Related Tasks</span></span>  
  
|<span data-ttu-id="24108-124">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="24108-124">Task Description</span></span>|<span data-ttu-id="24108-125">Tema</span><span class="sxs-lookup"><span data-stu-id="24108-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="24108-126">Crear una conexión a una base de datos de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24108-126">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="24108-127">Conectarse a un repositorio MDS &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="24108-127">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="24108-128">Cargar datos MDS en Excel.</span><span class="sxs-lookup"><span data-stu-id="24108-128">Load MDS data into Excel.</span></span>|[<span data-ttu-id="24108-129">Cargar datos de MDS en Excel</span><span class="sxs-lookup"><span data-stu-id="24108-129">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
|<span data-ttu-id="24108-130">Filtrar los datos MDS antes de cargarlos en Excel.</span><span class="sxs-lookup"><span data-stu-id="24108-130">Filter MDS data before you load it into Excel.</span></span>|[<span data-ttu-id="24108-131">Filtre los datos antes de cargar &#40;Complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="24108-131">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="24108-132">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="24108-132">Related Content</span></span>  
  
-   [<span data-ttu-id="24108-133">Cargando datos &#40;Complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="24108-133">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="24108-134">Archivos de consulta de acceso directo &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="24108-134">Shortcut Query Files &#40;MDS Add-in for Excel&#41;</span></span>](shortcut-query-files-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="24108-135">Complemento Master Data Services para Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="24108-135">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
