---
title: 'Tarea 9: configuración de un servicio de datos de referencia | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d0535fce-2bf5-4f6d-b517-ffe6fa13738d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1e7c685de13a2f5c495482f816818ff6b838fc7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751542"
---
# <a name="task-9-configuring-a-reference-data-service"></a><span data-ttu-id="9ea2d-102">Tarea 9: Configuración de un servicio de datos de referencia</span><span class="sxs-lookup"><span data-stu-id="9ea2d-102">Task 9: Configuring a Reference Data Service</span></span>
  <span data-ttu-id="9ea2d-103">En esta tarea, se configura DQS para usar un servicio de datos de referencia en Azure Marketplace.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-103">In this task, you configure DQS to use a Reference Data Service on Azure Marketplace.</span></span> <span data-ttu-id="9ea2d-104">En la tarea siguiente, configurará el dominio de **validación de direcciones** para utilizar este servicio.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-104">In the next task, you will configure the **Address Validation** domain to use this service.</span></span> <span data-ttu-id="9ea2d-105">En tiempo de ejecución, durante la actividad de limpieza, DQS pasa los valores de los dominios del dominio de **validación de direcciones** al servicio para su limpieza.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-105">At runtime, during cleansing activity, DQS passes the values of domains in the **Address Validation** domain to the service for cleansing.</span></span> <span data-ttu-id="9ea2d-106">Vea [configurar DQS para usar datos de referencia](https://msdn.microsoft.com/library/hh213070.aspx) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-106">See [Configure DQS to Use Reference Data](https://msdn.microsoft.com/library/hh213070.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="9ea2d-107">En la Página principal del **cliente DQS**, en el panel **Administración** , haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-107">In the main page of **DQS Client**, in the **Administration** pane, click **Configuration**.</span></span>  
  
2.  <span data-ttu-id="9ea2d-108">Asegúrese de que la pestaña **datos de referencia** está activa.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-108">Ensure that **Reference Data** tab is active.</span></span>  
  
3.  <span data-ttu-id="9ea2d-109">En el área **configuración de red** , escriba los valores adecuados en los campos **servidor proxy** y **Puerto** si necesita usar un servidor proxy para conectarse a Internet.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-109">In the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** fields if you need to use a proxy server to connect to Internet.</span></span>  
  
4.  <span data-ttu-id="9ea2d-110">Escriba la **clave de la cuenta de Azure Marketplace** para el campo ID. de **cuenta de datamarket** .</span><span class="sxs-lookup"><span data-stu-id="9ea2d-110">Type your **Azure Marketplace Account Key** for the **DataMarket Account ID** field.</span></span>  
  
     <span data-ttu-id="9ea2d-111">![Cuenta de servicio de datos de referencia de Azure Data Market](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Cuenta de servicio de datos de referencia de Azure Data Market")</span><span class="sxs-lookup"><span data-stu-id="9ea2d-111">![Azure Data Market Reference Data Service Account](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Azure Data Market Reference Data Service Account")</span></span>  
  
5.  <span data-ttu-id="9ea2d-112">Haga clic en el botón **validar** junto al cuadro de texto para validar el identificador de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-112">Click **Validate** button next to the text box to validate the account ID.</span></span>  
  
6.  <span data-ttu-id="9ea2d-113">Haga clic en **Aceptar** en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-113">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="9ea2d-114">Haga clic en **cerrar** en la parte inferior de la página para cambiar a la Página principal del cliente DQS.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-114">Click **Close** at the bottom of the page to switch to the main page of DQS Client.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="9ea2d-115">Tarea siguiente</span><span class="sxs-lookup"><span data-stu-id="9ea2d-115">Next Task</span></span>  
 [<span data-ttu-id="9ea2d-116">Tarea 10: Configuración de un dominio compuesto para usar un servicio de datos de referencia</span><span class="sxs-lookup"><span data-stu-id="9ea2d-116">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>](../../2014/tutorials/task-10-configuring-composite-domain-to-use-reference-data-service.md)  
  
  
