---
title: Diseñar la consulta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747505"
---
# <a name="design-the-query"></a><span data-ttu-id="b3225-102">Diseñar la consulta</span><span class="sxs-lookup"><span data-stu-id="b3225-102">Design the Query</span></span>
  <span data-ttu-id="b3225-103">Utilice esta página del Asistente para informes para crear una consulta escribiéndola manualmente, usando el Generador de consultas para crear una consulta de forma interactiva, o importando una consulta de otro informe.</span><span class="sxs-lookup"><span data-stu-id="b3225-103">Use this page of the Report Wizard to create a query by typing the query manually, by using Query Builder to interactively build a query, or by importing a query from another report.</span></span>  
  
 <span data-ttu-id="b3225-104">El tipo de origen de datos seleccionado en la página Seleccionar el origen de datos, una página anterior del Asistente para informes, determina la consulta que se puede escribir en esta página.</span><span class="sxs-lookup"><span data-stu-id="b3225-104">The data source type you chose on the Select the Data Source page, a previous page in the Report Wizard, determines the query you can enter on this page.</span></span> <span data-ttu-id="b3225-105">Por ejemplo, si el tipo de origen de datos es [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , puede escribir [!INCLUDE[tsql](../includes/tsql-md.md)] instrucciones o nombres de procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="b3225-105">For example, if the data source type is [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements or stored procedure names.</span></span> <span data-ttu-id="b3225-106">Si el tipo de origen de datos es [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , el panel consulta está deshabilitado y no se puede escribir una consulta directamente.</span><span class="sxs-lookup"><span data-stu-id="b3225-106">If the data source type is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], the Query pane is disabled and you cannot enter a query directly.</span></span> <span data-ttu-id="b3225-107">Puede especificar la consulta mediante el Generador de consultas.</span><span class="sxs-lookup"><span data-stu-id="b3225-107">You can specify the query by using Query Builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b3225-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="b3225-108">Options</span></span>  
 <span data-ttu-id="b3225-109">**Cadena de consulta**</span><span class="sxs-lookup"><span data-stu-id="b3225-109">**Query string**</span></span>  
 <span data-ttu-id="b3225-110">Escriba una consulta que recupere los datos que desea utilizar en el informe.</span><span class="sxs-lookup"><span data-stu-id="b3225-110">Type a query that retrieves the data you want to use in your report.</span></span>  
  
 <span data-ttu-id="b3225-111">**Generador de consultas**</span><span class="sxs-lookup"><span data-stu-id="b3225-111">**Query Builder**</span></span>  
 <span data-ttu-id="b3225-112">Haga clic en **Generador de consultas** para abrir un diseñador de consultas para el origen de datos o para importar una consulta de otro informe.</span><span class="sxs-lookup"><span data-stu-id="b3225-112">Click **Query Builder** to open a query designer for the data source, or to import a query from another report.</span></span>  
  
 <span data-ttu-id="b3225-113">Para obtener más información acerca de los diseñadores de consultas, vea [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span><span class="sxs-lookup"><span data-stu-id="b3225-113">For more information about query designers, see [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3225-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b3225-114">Example</span></span>  
 <span data-ttu-id="b3225-115">En el caso del tipo de origen de datos **Microsoft SQL Server**, la siguiente consulta recupera una lista de los apellidos de la tabla de base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] `Person` .</span><span class="sxs-lookup"><span data-stu-id="b3225-115">For the data source type **Microsoft SQL Server**, the following query retrieves a list of last names from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database `Person` table.</span></span>  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 <span data-ttu-id="b3225-116">En el caso del tipo de origen de datos **Microsoft SQL Server**, la siguiente consulta ejecuta el [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] procedimiento almacenado `uspGetEmployeeManagers` para el empleado con el número de identificación 1:</span><span class="sxs-lookup"><span data-stu-id="b3225-116">For the data source type **Microsoft SQL Server**, the following query runs the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] stored procedure `uspGetEmployeeManagers` for the employee with identification number 1:</span></span>  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3225-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3225-117">See Also</span></span>  
 <span data-ttu-id="b3225-118">[Ayuda del Asistente para informes](../../2014/reporting-services/report-wizard-help.md) </span><span class="sxs-lookup"><span data-stu-id="b3225-118">[Report Wizard Help](../../2014/reporting-services/report-wizard-help.md) </span></span>  
 <span data-ttu-id="b3225-119">[Conjuntos de valores integrados de informe y conjuntos de recursos compartidos &#40;Generador de informes y SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b3225-119">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b3225-120">Agregar datos a un informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b3225-120">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
