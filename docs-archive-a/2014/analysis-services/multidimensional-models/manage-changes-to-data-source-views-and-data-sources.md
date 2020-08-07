---
title: Administrar los cambios en las vistas del origen de datos y los orígenes de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data sources
- modifying data source views
- data source views [Analysis Services], schema updates
- data sources [Analysis Services], schema updates
ms.assetid: 928c9f63-365a-43fd-9bbd-78828cc7e54d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0f558ce6aaf9e57576d5773322352d33b81a3392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745442"
---
# <a name="manage-changes-to-data-source-views-and-data-sources"></a><span data-ttu-id="e607d-102">Administrar los cambios de las vistas del origen de datos y los orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="e607d-102">Manage Changes to Data Source Views and Data Sources</span></span>
  <span data-ttu-id="e607d-103">Si se vuelve a ejecutar el Asistente para generar esquemas, éste volverá a utilizar el mismo origen de datos y vista del origen de datos que en la generación original.</span><span class="sxs-lookup"><span data-stu-id="e607d-103">When the Schema Generation Wizard is rerun, it reuses the same data source and data source view that it used for the original generation.</span></span> <span data-ttu-id="e607d-104">Si se agrega un origen de datos o una vista de origen de datos, el asistente no los utilizará.</span><span class="sxs-lookup"><span data-stu-id="e607d-104">If you add a data source or a data source view, the wizard does not use it.</span></span> <span data-ttu-id="e607d-105">Si se elimina el origen de datos o la vista de origen de datos originales tras la generación inicial, debe ejecutarse el asistente desde el principio.</span><span class="sxs-lookup"><span data-stu-id="e607d-105">If you delete the original data source or data source view after the initial generation, you must run the wizard from the beginning.</span></span> <span data-ttu-id="e607d-106">También se eliminará la configuración anterior del asistente.</span><span class="sxs-lookup"><span data-stu-id="e607d-106">All previous settings in the wizard are also deleted.</span></span> <span data-ttu-id="e607d-107">Los objetos existentes en una base de datos subyacente enlazados a un origen de datos o vista de origen de datos eliminados se tratarán como objetos creados por el usuario la próxima vez que se ejecute el Asistente para generar esquemas.</span><span class="sxs-lookup"><span data-stu-id="e607d-107">Any existing objects in an underlying database that were bound to a deleted data source or data source view are treated as user-created objects the next time you run the Schema Generation Wizard.</span></span>  
  
 <span data-ttu-id="e607d-108">Si la vista del origen de datos no refleja el estado actual de la base de datos subyacente en el momento de la generación, el Asistente para generar esquemas podría experimentar errores al generar el esquema de la base de datos del área de asunto.</span><span class="sxs-lookup"><span data-stu-id="e607d-108">If the data source view does not reflect the actual state of the underlying database at the time of generation, the Schema Generation Wizard may encounter errors when it generates the schema for the subject area database.</span></span> <span data-ttu-id="e607d-109">Por ejemplo, si la vista del origen de datos especifica que el tipo de datos de una columna es **int**, pero el tipo de datos de la columna es en realidad **string**, el Asistente para generar esquemas establecerá el tipo de datos de la clave externa en **INT** para que coincida con la vista del origen de datos, aunque se producirá un error al crear la relación dado que el tipo de datos real es **string**.</span><span class="sxs-lookup"><span data-stu-id="e607d-109">For example, if the data source view specifies that the data type for a column is **int**, but data type for the column is actually **string**, the Schema Generation Wizard sets the data type for the foreign key to **INT** to match the data source view and then fails when it creates the relationship because the actual type is **string**.</span></span>  
  
 <span data-ttu-id="e607d-110">Por otra parte, no se generarán errores si se cambia la cadena de conexión de origen de datos a una base de datos distinta de la generación anterior.</span><span class="sxs-lookup"><span data-stu-id="e607d-110">On the other hand, if you change the data source connection string to a different database from the previous generation, no error is generated.</span></span> <span data-ttu-id="e607d-111">Se utilizará la nueva base de datos y no se realizarán cambios en la base de datos anterior.</span><span class="sxs-lookup"><span data-stu-id="e607d-111">The new database is used, and no change is made to the previous database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e607d-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e607d-112">See Also</span></span>  
 [<span data-ttu-id="e607d-113">Descripción de la generación incremental</span><span class="sxs-lookup"><span data-stu-id="e607d-113">Understanding Incremental Generation</span></span>](understanding-incremental-generation.md)  
  
  
