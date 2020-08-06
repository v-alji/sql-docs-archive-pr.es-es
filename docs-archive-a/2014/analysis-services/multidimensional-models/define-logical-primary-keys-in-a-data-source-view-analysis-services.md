---
title: Definir claves principales lógicas en una vista del origen de datos (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- removing logical primary keys
- logical primary keys [SQL Server]
- deleting logical primary keys
- data source views [Analysis Services], logical primary keys
ms.assetid: 172bc267-c637-4caa-bf55-0ba198d30b1e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25092e5d754381c572dcdbfc03e5ee0f29c1df24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673382"
---
# <a name="define-logical-primary-keys-in-a-data-source-view-analysis-services"></a><span data-ttu-id="a3cdc-102">Definir claves principales lógicas en una vista del origen de datos (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="a3cdc-102">Define Logical Primary Keys in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="a3cdc-103">El Asistente para vistas del origen de datos y el Diseñador de vistas del origen de datos definen automáticamente una clave principal para una tabla que se agrega a una vista del origen de datos basada en una tabla de base de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-103">The Data Source View Wizard and Data Source View Designer automatically define a primary key for a table that is added to a data source view based on underlying database table.</span></span>  
  
 <span data-ttu-id="a3cdc-104">En ocasiones, podría ser necesario definir manualmente una clave principal en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-104">Occasionally, you may need to manually define a primary key in the data source view.</span></span> <span data-ttu-id="a3cdc-105">Por ejemplo, por motivos de rendimiento o diseño, es posible que las tablas de un origen de datos no tengan definidas de forma explícita columnas de clave principal.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-105">For example, for performance or design reasons, tables in a data source may not have explicitly defined primary key columns.</span></span> <span data-ttu-id="a3cdc-106">Las consultas con nombre y las vistas también pueden pasar por alto la columna de clave principal de una tabla.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-106">Named queries and views may also omit the primary key column for a table.</span></span> <span data-ttu-id="a3cdc-107">Si una tabla, vista o consulta con nombre no tiene definida una clave principal física, puede definir manualmente una clave principal lógica en la tabla, vista o consulta con nombre en el Diseñador de vistas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-107">If a table, view, or named query does not have a physical primary key defined, you can manually define a logical primary key on the table, view or named query in Data Source View Designer.</span></span>  
  
## <a name="set-a-logical-primary-key"></a><span data-ttu-id="a3cdc-108">Establecer una clave principal lógica</span><span class="sxs-lookup"><span data-stu-id="a3cdc-108">Set a Logical Primary Key</span></span>  
 <span data-ttu-id="a3cdc-109">La claves principales son necesarias en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para identificar de manera exclusiva los registros de una tabla, identificar las columnas de clave en las tablas de dimensiones y admitir relaciones entre tablas, vistas y consultas con nombre.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-109">Primary keys are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to uniquely identify records in a table, identify key columns in dimension tables and to support relationships between tables, views and named queries.</span></span> <span data-ttu-id="a3cdc-110">Estas relaciones se usan para crear consultas para la recuperación de datos y metadatos de orígenes de datos subyacentes y para usar las características avanzadas de Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-110">These relationships are used to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="a3cdc-111">Se puede usar cualquier columna para la clave principal lógica, incluido un cálculo con nombre.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-111">Any column can be used for the logical primary key, including a named calculation.</span></span> <span data-ttu-id="a3cdc-112">Cuando crea una clave principal lógica, se crea una restricción exclusiva en la vista del origen de datos y se marca como una restricción de clave principal.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-112">When you create a logical primary key, a unique constraint is created in the data source view and marked as a primary key constraint.</span></span> <span data-ttu-id="a3cdc-113">Cualquier otra clave principal lógica existente especificada en la tabla seleccionada se elimina.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-113">Any other existing logical primary key specified in the selected table is deleted.</span></span>  
  
1.  <span data-ttu-id="a3cdc-114">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto o conéctese a la base de datos que contiene la vista del origen de datos en que desea establecer una clave principal lógica.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to set a logical primary key.</span></span>  
  
2.  <span data-ttu-id="a3cdc-115">En el Explorador de soluciones, expanda la carpeta **Vistas del origen de datos** y, después, haga doble clic en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-115">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>  
  
     <span data-ttu-id="a3cdc-116">Para buscar una tabla o vista, puede usar la opción **Buscar tabla** si hace clic en el menú **Vista del origen de datos**  o hace clic con el botón derecho en una zona abierta de los paneles **Tablas** o **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="a3cdc-116">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View**  menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
3.  <span data-ttu-id="a3cdc-117">En los paneles **Tablas** o **Diagrama** , haga clic con el botón derecho en las columnas que quiera usar para definir una clave principal lógica y, después, haga clic en **Establecer clave principal lógica**.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-117">In either the **Tables** or the **Diagram** pane, right-click the column or columns that you want to use to define a logical primary key, and then click **Set Logical Primary Key**.</span></span>  
  
     <span data-ttu-id="a3cdc-118">La opción para establecer una clave principal lógica únicamente está disponible en las tablas que no tienen una clave principal.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-118">The option to set a logical primary key is available only for tables that do not have a primary key.</span></span>  
  
     <span data-ttu-id="a3cdc-119">Observe que, una vez establecida la clave, aparece un icono de llave que identifica las columnas de clave principal.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-119">Notice that after you set the key, a key icon now identifies the primary key columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3cdc-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3cdc-120">See Also</span></span>  
 <span data-ttu-id="a3cdc-121">[Vistas del origen de datos en modelos multidimensionales](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="a3cdc-121">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="a3cdc-122">Definir cálculos con nombre en una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a3cdc-122">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
