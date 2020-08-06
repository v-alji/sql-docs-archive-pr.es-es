---
title: Importar desde un origen de datos multidimensionales (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7f0793ea-a4c7-42e9-b722-2164a454ebca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b26cc8ed7237f87fa5e23c6a2fd47e18de2c165
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677269"
---
# <a name="import-from-a-multidimensional-data-source-ssas-tabular"></a><span data-ttu-id="207bd-102">Importar datos de un origen de datos multidimensionales (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="207bd-102">Import from a Multidimensional Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="207bd-103">Puede usar una base de datos de cubo de Analysis Services como origen de datos para un modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="207bd-103">You can use an Analysis Services cube database as a data source for a tabular model.</span></span> <span data-ttu-id="207bd-104">Para importar datos de un cubo de Analysis Services, debe definir una consulta MDX para seleccionar los datos que desea importar.</span><span class="sxs-lookup"><span data-stu-id="207bd-104">In order to import data from an Analysis Services cube, you must define an MDX Query to select data to import.</span></span>  
  
 <span data-ttu-id="207bd-105">Cualquier dato contenido en una base de datos de SQL Server Analysis Services se puede importar en un modelo.</span><span class="sxs-lookup"><span data-stu-id="207bd-105">Any data that is contained in a SQL Server Analysis Services database can be imported into a model.</span></span> <span data-ttu-id="207bd-106">Puede extraer todo el contenido o parte de una dimensión, u obtener segmentos y agregados del cubo, como la suma de ventas, mes a mes, durante el año actual, etc. No obstante, debería tener presente que todos los datos que se importan de un cubo pierden la información de estructura jerárquica.</span><span class="sxs-lookup"><span data-stu-id="207bd-106">You can extract all or part of a dimension, or get slices and aggregates from the cube, such as the sum of sales, month by month, for the current year, etc. However, you should keep in mind all data that you import from a cube is flattened.</span></span> <span data-ttu-id="207bd-107">Por consiguiente, si define una consulta que recupera medidas a lo largo de varias dimensiones, los datos se importarán con cada dimensión en una columna independiente.</span><span class="sxs-lookup"><span data-stu-id="207bd-107">Therefore, if you define a query that retrieves measures along multiple dimensions, the data will be imported with each dimension in a separate column.</span></span>  
  
 <span data-ttu-id="207bd-108">Los cubos de Analysis Services deben ser de la versión SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]o [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="207bd-108">Analysis Services cubes must be version SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
### <a name="to-import-data-from-an-analysis-services-cube"></a><span data-ttu-id="207bd-109">Para importar datos de un cubo de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="207bd-109">To import data from an Analysis Services cube</span></span>  
  
1.  <span data-ttu-id="207bd-110">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], haga clic en el menú **Modelo** y, a continuación, haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="207bd-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="207bd-111">En la página **Conectarse a un origen de datos** , seleccione **Microsoft Analysis Services**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="207bd-111">On the **Connect to a Data Source** page, select **Microsoft Analysis Services**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="207bd-112">Siga los pasos en el Asistente para la importación de tablas.</span><span class="sxs-lookup"><span data-stu-id="207bd-112">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="207bd-113">Podrá especificar una consulta MDX en la página de **Especificar una consulta MDX** .</span><span class="sxs-lookup"><span data-stu-id="207bd-113">You will be able to specify an MDX query on the **Specify a MDX Query** page.</span></span> <span data-ttu-id="207bd-114">Para usar el Diseñador de consultas MDX, haga clic en **Diseño**en la página Especificar una consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="207bd-114">To use the MDX Query Designer, on the Specify a MDX Query page, click **Design**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="207bd-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="207bd-115">See Also</span></span>  
 <span data-ttu-id="207bd-116">[Importar datos &#40;&#41;tabular de SSAS](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="207bd-116">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="207bd-117">Orígenes de datos compatibles &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="207bd-117">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
