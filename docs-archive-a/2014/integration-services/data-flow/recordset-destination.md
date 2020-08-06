---
title: Destino de conjunto de registros | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.recordsetdest.f1
helpviewer_keywords:
- Recordset destination
- ADO recordsets [Integration Services]
- destinations [Integration Services], Recordset
- in-memory ADO recordsets [Integration Services]
ms.assetid: be973cf1-c4ff-49f8-987e-314c08ef98e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1acc29c904e9020721e8ac62dff09a8ec29a392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670451"
---
# <a name="recordset-destination"></a><span data-ttu-id="3dd25-102">destino de conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="3dd25-102">Recordset Destination</span></span>
  <span data-ttu-id="3dd25-103">El destino de conjunto de registros crea y llena un conjunto de registros ADO almacenado en la memoria.</span><span class="sxs-lookup"><span data-stu-id="3dd25-103">The Recordset destination creates and populates an in-memory ADO recordset.</span></span> <span data-ttu-id="3dd25-104">La forma del conjunto de registros se define según la entrada al destino de conjunto de registros en el tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="3dd25-104">The shape of the recordset is defined by the input to the Recordset destination at design time.</span></span>  
  
## <a name="configuration-of-the-recordset-destination"></a><span data-ttu-id="3dd25-105">Configuración del destino de conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="3dd25-105">Configuration of the Recordset Destination</span></span>  
 <span data-ttu-id="3dd25-106">El destino de conjunto de registros se configura especificando la variable que almacena el conjunto de registros ADO.</span><span class="sxs-lookup"><span data-stu-id="3dd25-106">You configure the Recordset destination by specifying the variable that stores the ADO recordset.</span></span>  
  
 <span data-ttu-id="3dd25-107">En tiempo de ejecución, el conjunto de registros ADO se escribe en la variable de tipo Object especificada en la propiedad VariableName del destino de conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="3dd25-107">At run time, an ADO recordset is written to the variable of type, Object, that is specified in the VariableName property of the Recordset destination.</span></span> <span data-ttu-id="3dd25-108">A continuación, la variable pone el conjunto de registros a disposición fuera del flujo de datos, donde lo pueden usar scripts y otros elementos del paquete.</span><span class="sxs-lookup"><span data-stu-id="3dd25-108">The variable then makes the Recordset available outside the data flow, where it can be used by scripts and other package elements.</span></span>  
  
 <span data-ttu-id="3dd25-109">Este origen tiene una entrada.</span><span class="sxs-lookup"><span data-stu-id="3dd25-109">This source has one input.</span></span> <span data-ttu-id="3dd25-110">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="3dd25-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="3dd25-111">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="3dd25-111">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="3dd25-112">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="3dd25-112">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="3dd25-113">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3dd25-113">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="3dd25-114">Common Properties</span><span class="sxs-lookup"><span data-stu-id="3dd25-114">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="3dd25-115">Propiedades personalizadas del destino de conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="3dd25-115">Recordset Destination Custom Properties</span></span>](recordset-destination-custom-properties.md)  
  
 <span data-ttu-id="3dd25-116">Para más información sobre cómo establecer las propiedades, vea [Establecer las propiedades de un componente de flujo de datos](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="3dd25-116">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="3dd25-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="3dd25-117">Related Tasks</span></span>  
 [<span data-ttu-id="3dd25-118">Usar un destino de conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="3dd25-118">Use a Recordset Destination</span></span>](recordset-destination.md)  
  
  
