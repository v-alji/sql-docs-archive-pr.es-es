---
title: Aplicar reglas de calidad de los datos al origen de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a965e8f2-004d-4ccc-8523-a185b35b26e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d59e6fb5ffb752b3346d40740e0b841bf574344e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744216"
---
# <a name="apply-data-quality-rules-to-data-source"></a><span data-ttu-id="c4163-102">Aplicar reglas de calidad de los datos al origen de datos</span><span class="sxs-lookup"><span data-stu-id="c4163-102">Apply Data Quality Rules to Data Source</span></span>
  <span data-ttu-id="c4163-103">Puede utilizar Data Quality Services (DQS) para corregir los datos en el flujo de datos de paquete conectando la transformación de Limpieza de DQS con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c4163-103">You can use Data Quality Services (DQS) to correct data in the package data flow by connecting the DQS Cleansing transformation to the data source.</span></span> <span data-ttu-id="c4163-104">Para obtener más información acerca de DQS, vea [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="c4163-104">For more information about DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span> <span data-ttu-id="c4163-105">Para obtener más información sobre la transformación, vea [DQS Cleansing Transformation](dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c4163-105">For more information about the transformation, see [DQS Cleansing Transformation](dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="c4163-106">Al procesar datos con la transformación Limpieza DQS, se crea un proyecto de calidad de datos en el servidor Data Quality Server.</span><span class="sxs-lookup"><span data-stu-id="c4163-106">When you process data with the DQS Cleansing transformation, a data quality project is created on the Data Quality Server.</span></span> <span data-ttu-id="c4163-107">Utilice Data Quality Client para administrar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c4163-107">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="c4163-108">Para obtener más información, vea [Administrar &#40;abrir, desbloquear, cambiar nombre y eliminar&#41; un proyecto de calidad de los datos](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span><span class="sxs-lookup"><span data-stu-id="c4163-108">For more information, see [Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span></span>  
  
### <a name="to-correct-data-in-the-data-flow"></a><span data-ttu-id="c4163-109">Para corregir datos en el flujo de datos</span><span class="sxs-lookup"><span data-stu-id="c4163-109">To correct data in the data flow</span></span>  
  
1.  <span data-ttu-id="c4163-110">Cree un paquete.</span><span class="sxs-lookup"><span data-stu-id="c4163-110">Create a package.</span></span>  
  
2.  <span data-ttu-id="c4163-111">Agregue y configure la transformación Limpieza de DQS.</span><span class="sxs-lookup"><span data-stu-id="c4163-111">Add and configure the DQS Cleansing transformation.</span></span> <span data-ttu-id="c4163-112">Para más información, consulte [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="c4163-112">For more information, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="c4163-113">Conecte la transformación Limpieza de DQS a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c4163-113">Connect the DQS Cleansing transformation to a data source.</span></span>  
  
  
