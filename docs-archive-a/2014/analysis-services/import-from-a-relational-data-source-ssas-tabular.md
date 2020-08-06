---
title: Importar desde un origen de datos relacional (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 043201cc-fbef-4ed0-bde8-dc5e3a3e8bea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93bb9ba9ba8d40262e4e90e840dcd15ac6826df3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676717"
---
# <a name="import-from-a-relational-data-source-ssas-tabular"></a><span data-ttu-id="b63dd-102">Importar datos de un origen de datos relacionales (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="b63dd-102">Import from a Relational Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="b63dd-103">Con el Asistente para la importación de tablas, puede importar datos desde una variedad de bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="b63dd-103">You can import data from a variety of relational databases by using the Table Import Wizard.</span></span> <span data-ttu-id="b63dd-104">El asistente está disponible en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], en el menú **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="b63dd-104">The wizard is available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Model** menu.</span></span> <span data-ttu-id="b63dd-105">Para conectarse a un origen de datos, debe tener instalado en el equipo el proveedor adecuado.</span><span class="sxs-lookup"><span data-stu-id="b63dd-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span> <span data-ttu-id="b63dd-106">Para más información sobre los proveedores y los orígenes de datos admitidos, vea [Orígenes de datos compatibles &#40;SSAS tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="b63dd-106">For more information about supported data sources and providers, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="b63dd-107">El Asistente para la importación de tablas permite importar datos de los orígenes de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b63dd-107">The Table Import Wizard supports importing data from the following data sources:</span></span>  
  
 <span data-ttu-id="b63dd-108">**Bases de datos relacionales**</span><span class="sxs-lookup"><span data-stu-id="b63dd-108">**Relational Databases**</span></span>  
  
-   <span data-ttu-id="b63dd-109">Base de datos de Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="b63dd-109">Microsoft SQL Server database</span></span>  
  
-   <span data-ttu-id="b63dd-110">Microsoft SQL Azure</span><span class="sxs-lookup"><span data-stu-id="b63dd-110">Microsoft SQL Azure</span></span>  
  
-   <span data-ttu-id="b63dd-111">Base de datos de Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="b63dd-111">Microsoft Access database</span></span>  
  
-   <span data-ttu-id="b63dd-112">Almacenamiento de datos paralelo de Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="b63dd-112">Microsoft SQL Server Parallel Data Warehouse</span></span>  
  
-   <span data-ttu-id="b63dd-113">Oracle</span><span class="sxs-lookup"><span data-stu-id="b63dd-113">Oracle</span></span>  
  
-   <span data-ttu-id="b63dd-114">Teradata</span><span class="sxs-lookup"><span data-stu-id="b63dd-114">Teradata</span></span>  
  
-   <span data-ttu-id="b63dd-115">Sybase</span><span class="sxs-lookup"><span data-stu-id="b63dd-115">Sybase</span></span>  
  
-   <span data-ttu-id="b63dd-116">Informix</span><span class="sxs-lookup"><span data-stu-id="b63dd-116">Informix</span></span>  
  
-   <span data-ttu-id="b63dd-117">IBM DB2</span><span class="sxs-lookup"><span data-stu-id="b63dd-117">IBM DB2</span></span>  
  
-   <span data-ttu-id="b63dd-118">OLE DB/ODBC</span><span class="sxs-lookup"><span data-stu-id="b63dd-118">OLE DB/ODBC</span></span>  
  
 <span data-ttu-id="b63dd-119">**Orígenes multidimensionales**</span><span class="sxs-lookup"><span data-stu-id="b63dd-119">**Multidimensional Sources**</span></span>  
  
-   <span data-ttu-id="b63dd-120">Cubo de Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b63dd-120">Microsoft SQL Server Analysis Services cube</span></span>  
  
 <span data-ttu-id="b63dd-121">El Asistente para la importación de tablas no permite importar datos de un libro de [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b63dd-121">The Table Import Wizard does not support importing data from a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] Workbook as a data source.</span></span>  
  
### <a name="to-import-data-from-a-database"></a><span data-ttu-id="b63dd-122">Para importar datos de una base de datos</span><span class="sxs-lookup"><span data-stu-id="b63dd-122">To import data from a database</span></span>  
  
1.  <span data-ttu-id="b63dd-123">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], haga clic en el menú **Modelo** y, a continuación, haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="b63dd-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="b63dd-124">En la página **Conectarse a un origen de datos** , seleccione el tipo de base de datos con el que desea conectar y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b63dd-124">On the **Connect to a Data Source** page, select the type of database to connect to, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="b63dd-125">Siga los pasos en el Asistente para la importación de tablas.</span><span class="sxs-lookup"><span data-stu-id="b63dd-125">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="b63dd-126">En las páginas siguientes, podrá seleccionar tablas y vistas específicas o aplicar filtros mediante la página **Seleccionar tablas y vistas** o mediante la creación de una consulta SQL en la página **Especificar una consulta SQL** .</span><span class="sxs-lookup"><span data-stu-id="b63dd-126">On subsequent pages, you will be able to select specific tables and views or apply filters by using the **Select Tables and Views** page or by creating a SQL query on **Specify a SQL Query** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b63dd-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b63dd-127">See Also</span></span>  
 <span data-ttu-id="b63dd-128">[Importar datos &#40;&#41;tabular de SSAS](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b63dd-128">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="b63dd-129">Orígenes de datos compatibles &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="b63dd-129">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
