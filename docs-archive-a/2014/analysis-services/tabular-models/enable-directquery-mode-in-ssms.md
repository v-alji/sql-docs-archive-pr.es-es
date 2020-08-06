---
title: Configurar el acceso in-Memory o DirectQuery para una base de datos de modelo tabular | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5d439a9-5be1-4145-90e8-90777d80e98b
author: minewiskan
ms.author: owend
ms.openlocfilehash: a607bc6c11f35736487932bdf10d239afc8b5355
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744378"
---
# <a name="configure-in-memory-or-directquery-access-for-a-tabular-model-database"></a><span data-ttu-id="56b96-102">Configurar el acceso In-Memory o DirectQuery para una base de datos modelo tabular</span><span class="sxs-lookup"><span data-stu-id="56b96-102">Configure In-Memory or DirectQuery Access for a Tabular Model Database</span></span>
  <span data-ttu-id="56b96-103">En este tema se describe cómo cambiar las propiedades de conexión de un modelo tabular que ya se haya implementado, para habilitar el uso del modelo en el modo Direct Query.</span><span class="sxs-lookup"><span data-stu-id="56b96-103">This topic describes how to change the connection properties of a tabular model that has already been deployed, to enable use of the model in Direct Query mode.</span></span>  
  
 <span data-ttu-id="56b96-104">Para obtener más información sobre estas propiedades y la configuración de los escenarios más comunes, vea [escenarios de implementación de DirectQuery &#40;&#41;tabular de SSAS ](../directquery-deployment-scenarios-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="56b96-104">For more information about these properties, and configuration for the most common scenarios, see [DirectQuery Deployment Scenarios &#40;SSAS Tabular&#41;](../directquery-deployment-scenarios-ssas-tabular.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56b96-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56b96-105">Requirements</span></span>  
 <span data-ttu-id="56b96-106">Habilitar el uso del modo Direct Query en un modelo tabular es un proceso de varias fases.</span><span class="sxs-lookup"><span data-stu-id="56b96-106">Enabling the use of Direct Query mode on a tabular model is a multistep process.</span></span> <span data-ttu-id="56b96-107">Debe:</span><span class="sxs-lookup"><span data-stu-id="56b96-107">You must:</span></span>  
  
1.  <span data-ttu-id="56b96-108">Asegurarse de que el modelo no tiene características que podrían ocasionar errores de validación en el modo Direct Query.</span><span class="sxs-lookup"><span data-stu-id="56b96-108">Ensure that the model does not have features which might cause validation errors in Direct Query mode.</span></span>  
  
2.  <span data-ttu-id="56b96-109">Cambiar el modo de almacenamiento en el modelo para admitir Direct Query.</span><span class="sxs-lookup"><span data-stu-id="56b96-109">Change the storage mode on the model to support Direct Query.</span></span>  
  
3.  <span data-ttu-id="56b96-110">Implementar el modelo en un modo que admita consultas en el modo Direct Query híbrido o puro.</span><span class="sxs-lookup"><span data-stu-id="56b96-110">Deploy the model in a mode that supports queries in either a hybrid or pure Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="56b96-111">Modificar la cadena de conexión en la base de datos implementada para admitir el modo Direct Query.</span><span class="sxs-lookup"><span data-stu-id="56b96-111">Edit the connection string on the deployed database to support Direct Query mode.</span></span>  
  
 <span data-ttu-id="56b96-112">En este tema se supone que ha creado y ha validado el modelo, y solo necesita habilitar el acceso Direct Query desde un cliente como [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56b96-112">This topic assumes that you have created and validated your model, and only need to enable Direct Query access from a client such as [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="56b96-113">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="56b96-113">Procedure</span></span>  
  
#### <a name="change-the-connection-string-properties-of-the-model"></a><span data-ttu-id="56b96-114">Cambiar las propiedades de una cadena de conexión del modelo</span><span class="sxs-lookup"><span data-stu-id="56b96-114">Change the Connection String Properties of the Model</span></span>  
  
1.  <span data-ttu-id="56b96-115">En SQL Server Management Studio, abra la instancia en la que se implementó el modelo.</span><span class="sxs-lookup"><span data-stu-id="56b96-115">In SQL Server Management Studio, open the instance to which you deployed the model.</span></span>  
  
2.  <span data-ttu-id="56b96-116">En Explorador de objetos, haga clic con el botón secundario en el nombre de la base de datos modelo y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="56b96-116">In Object Explorer, right-click the name of the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="56b96-117">Busque la propiedad **DirectQueryMode**.</span><span class="sxs-lookup"><span data-stu-id="56b96-117">Locate the property, **DirectQueryMode**.</span></span> <span data-ttu-id="56b96-118">Para habilitar el uso del origen de datos relacional, esta propiedad se debe establecer en uno de estos valores:</span><span class="sxs-lookup"><span data-stu-id="56b96-118">To enable use of the relational data source, this property must be set to one of these values:</span></span>  
  
    -   <span data-ttu-id="56b96-119">**DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="56b96-119">**DirectQuery**</span></span>  
  
    -   <span data-ttu-id="56b96-120">**InMemoryWithDirectQuery**</span><span class="sxs-lookup"><span data-stu-id="56b96-120">**InMemoryWithDirectQuery**</span></span>  
  
    -   <span data-ttu-id="56b96-121">**DirectQueryWithInMemory**</span><span class="sxs-lookup"><span data-stu-id="56b96-121">**DirectQueryWithInMemory**</span></span>  
  
  
