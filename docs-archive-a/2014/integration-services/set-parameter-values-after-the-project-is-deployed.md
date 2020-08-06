---
title: Establecer los valores de los parámetros después de implementar el proyecto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c9dcca4d-f1a0-45ec-b078-f4d372589baf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39572594e429b61de0641c6e6929e84105138f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751290"
---
# <a name="set-parameter-values-after-the-project-is-deployed"></a><span data-ttu-id="dd0c9-102">Establecer valores de parámetro después de la implementación del proyecto</span><span class="sxs-lookup"><span data-stu-id="dd0c9-102">Set Parameter Values After the Project Is Deployed</span></span>
  <span data-ttu-id="dd0c9-103">El Asistente para la implementación permite establecer valores de parámetro predeterminados del servidor al implementar el proyecto en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-103">The Deployment Wizard allows you to set server default parameter values when you deploy your project to the catalog.</span></span> <span data-ttu-id="dd0c9-104">Después de que el proyecto esté en el catálogo, puede utilizar el Explorador de objetos de SQL Server Management Studio (SSMS) o Transact-SQL para establecer valores predeterminados del servidor.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-104">After your project is in the catalog, you can use SQL Server Management Studio (SSMS) Object Explorer or Transact-SQL to set server default values.</span></span>  
  
### <a name="to-set-server-defaults-with-ssms-object-explorer"></a><span data-ttu-id="dd0c9-105">Para establecer valores predeterminados del servidor con el Explorador de objetos de SSMS:</span><span class="sxs-lookup"><span data-stu-id="dd0c9-105">To set server defaults with SSMS Object Explorer:</span></span>  
  
1.  <span data-ttu-id="dd0c9-106">Seleccione y haga clic con el botón derecho en el proyecto debajo del nodo **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-106">Select and right-click the project under the **Integration Services** node.</span></span>  
  
2.  <span data-ttu-id="dd0c9-107">Haga clic en **Propiedades** para abrir el cuadro de diálogo **Propiedades del proyecto** .</span><span class="sxs-lookup"><span data-stu-id="dd0c9-107">Click **Properties** to open the **Project Properties** dialog window.</span></span>  
  
3.  <span data-ttu-id="dd0c9-108">Abra la página de parámetros haciendo clic en **Parámetros** debajo de **Seleccionar una página**.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-108">Open the parameters page by clicking **Parameters** under **Select a page**.</span></span>  
  
4.  <span data-ttu-id="dd0c9-109">Seleccione el parámetro deseado en la lista **Parámetros** .</span><span class="sxs-lookup"><span data-stu-id="dd0c9-109">Select the desired parameter in the **Parameters** list.</span></span> <span data-ttu-id="dd0c9-110">Nota: la columna **Contenedor** ayuda a distinguir los parámetros del proyecto de los parámetros del paquete.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-110">Note: The **Container** column helps distinguish project parameters from package parameters.</span></span>  
  
5.  <span data-ttu-id="dd0c9-111">En la columna de **Valor** , especifique el valor del parámetro predeterminado del servidor deseado.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-111">In the **Value** column, specify the desired server default parameter value.</span></span>  
  
 <span data-ttu-id="dd0c9-112">Para establecer valores predeterminados del servidor con Transact-SQL, use el procedimiento almacenado de [catalog.set_object_parameter_value &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="dd0c9-112">To set server defaults with Transact-SQL, use the [catalog.set_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database) stored procedure.</span></span> <span data-ttu-id="dd0c9-113">Para ver los valores predeterminados actuales del servidor, consulte la vista [catalog.object_parameters &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="dd0c9-113">To view current server defaults, query the [catalog.object_parameters &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database) view.</span></span> <span data-ttu-id="dd0c9-114">Para borrar un valor predeterminado del servidor, use el procedimiento almacenado [catalog.clear_object_parameter_value &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="dd0c9-114">To clear a server default value, use the [catalog.clear_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database) stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd0c9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd0c9-115">See Also</span></span>  
 [<span data-ttu-id="dd0c9-116">Integration Services &#40;los parámetros de&#41; SSIS</span><span class="sxs-lookup"><span data-stu-id="dd0c9-116">Integration Services &#40;SSIS&#41; Parameters</span></span>](integration-services-ssis-package-and-project-parameters.md)  
  
  
