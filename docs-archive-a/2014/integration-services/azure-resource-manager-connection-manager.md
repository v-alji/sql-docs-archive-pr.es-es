---
title: Administrador de conexiones de Azure Resource Manager | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPARMCM.F1
- SQL11.DTS.DESIGNER.AFPARMCM.F1
ms.assetid: a2380258-0418-4a8c-a731-5071a44ddf1e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1dce4def11f14072295dbf3cde9d5ab77304fe74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673871"
---
# <a name="azure-resource-manager-connection-manager"></a><span data-ttu-id="a0c64-102">Administrador de conexiones de Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="a0c64-102">Azure Resource Manager Connection Manager</span></span>
<span data-ttu-id="a0c64-103">El **Administrador de conexiones de Azure Resource Manager** permite que un paquete SSIS administre los recursos de Azure con una [entidad de servicio](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span><span class="sxs-lookup"><span data-stu-id="a0c64-103">The **Azure Resource Manager Connection Manager** enables an SSIS package to manage Azure resources using a [service principal](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span></span>

<span data-ttu-id="a0c64-104">Para crear y configurar un **Administrador de conexiones de Azure Resource Manager**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a0c64-104">To create and configure an **Azure Resource Manager Connection Manager**, follow the steps below:</span></span>

1. <span data-ttu-id="a0c64-105">En el cuadro de diálogo **Agregar administrador de conexiones SSIS**, seleccione **AzureResourceManager** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a0c64-105">In the **Add SSIS Connection Manager** dialog box, select **AzureResourceManager**, and click **Add**.</span></span>
2. <span data-ttu-id="a0c64-106">En el cuadro de diálogo **Azure Resource Manager Connection Manager Editor** (Editor del Administrador de conexiones de Azure Resource Manager), especifique el **id. de aplicación**, la **clave de aplicación** y el **id. de inquilino** de la entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="a0c64-106">In the **Azure Resource Manager Connection Manager Editor** dialog box, specify the **Application ID**, **Application Key**, and **Tenant ID** for the service principal.</span></span> <span data-ttu-id="a0c64-107">Para obtener más información acerca de estas propiedades, consulte [este](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal) artículo.</span><span class="sxs-lookup"><span data-stu-id="a0c64-107">For details about these properties, please refer to [this](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal) article.</span></span>
3. <span data-ttu-id="a0c64-108">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a0c64-108">Click **OK** to close the dialog box.</span></span>
4. <span data-ttu-id="a0c64-109">Puede ver las propiedades del Administrador de conexiones que creó en la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="a0c64-109">You can see the properties of the connection manager you created in the **Properties** window.</span></span>
